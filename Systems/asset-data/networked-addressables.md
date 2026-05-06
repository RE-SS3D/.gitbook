# Networked Addressables

FishNet must know a network prefab before a spawn message arrives. Addressables can load prefabs at runtime, so `AssetSubSystem` adds a preload and registration layer around FishNet spawning.

Use this page when a prefab loaded through `AssetSubSystem` has a root `NetworkObject`.

## The short rule

Use `NetworkSpawner.SpawnAsync(...)` for addressable prefabs loaded through `AssetSubSystem`.

Use `NetworkSpawner.Spawn(...)` only for scene objects, directly referenced prefabs, or other objects that are already present on every client without Addressables synchronization.

## Spawn by generated ID

This path loads the prefab, waits for clients, instantiates it, spawns it, tracks it for late joiners, and releases the temporary load handle.

```csharp
using FishNet.Object;
using SS3D.Data.Generated;
using SS3D.Data.Networking;

NetworkObject spawned = await NetworkSpawner.SpawnAsync(Items.BikeHorn);
```

## Spawn an existing instance

If another system already loaded and instantiated the prefab, pass the same asset key when spawning.

```csharp
AssetHandle<GameObject> handle = await new AssetRequest<GameObject>(Items.BikeHorn).LoadAsync();

if (!handle)
{
    handle?.Dispose();
    return;
}

GameObject instance = Object.Instantiate(handle.Asset);
await NetworkSpawner.SpawnAsync(instance, Items.BikeHorn);
handle.Dispose();
```

The asset key tells `NetworkBarrier` which prefab clients must load before FishNet spawns the object.

`ObjectAssetReference` overloads use `assetReference.Id` as the same key:

```csharp
await NetworkSpawner.SpawnAsync(instance, tileObjectSo.PrefabAsset);
```

## What the barrier does

`AssetSubSystem` spawns a `NetworkBarrier` prefab on the server after the server starts. Before an addressable network prefab is spawned:

1. The server asks the barrier to ensure all clients are ready for the asset GUID.
2. Clients receive an RPC and call `new AssetRequest<Object>(key).LoadAsync()`.
3. Each client stores a local handle so the prefab stays loaded and registered.
4. Clients report success or failure back to the server.
5. The server continues spawning only if the barrier succeeds before timeout.

When the last active network instance for a GUID is released, the barrier broadcasts an unload so clients can release their local handles.

## Late joiners

Late joiners need prefabs for objects already active in the world. `NetworkBarrier` tracks active network-spawned asset keys and sends a preload snapshot to each client after start scenes load.

`PreloadCondition` gates normal observer visibility until that preload snapshot completes. This prevents a client from observing addressable objects before the matching prefab is loaded and registered.

Global objects that ignore the observer manager, such as the barrier itself, are unaffected.

## NetworkObjects generation

`NetworkObjects` replaces a direct FishNet prefab collection with a deterministic GUID-backed collection.

The editor generator:

* scans prefabs with root `NetworkObject` components
* sorts them by GUID so prefab IDs stay stable across machines
* serializes non-addressable prefabs directly into runtime slots
* leaves addressable prefab slots empty until the asset is loaded
* stamps network prefabs with `AssetIdentifier` and `NetworkObjectTracker`
* stores the generated collection at `Assets/Content/Data/AssetSystem/NetworkObjects.asset`

At runtime, loaded addressable prefabs are discovered through `NetworkObjectTracker` and inserted into the correct FishNet slot.

The generator settings live at `ProjectSettings/SS3D/Assets/NetworkObjectsGeneratorSettings.asset`.

## Why direct FishNet spawning is unsafe

The old Asset Data flow could usually synchronously resolve a prefab before spawning. With dynamic Addressables, the server can load a prefab that clients do not have yet. A direct `InstanceFinder.ServerManager.Spawn(...)` can therefore send a spawn for an unknown prefab ID.

`NetworkSpawner.SpawnAsync(...)` is the safe addressable path because it waits for the preload barrier and keeps clients holding the loaded prefab handle.

## Adding a network prefab checklist

1. Add the prefab to an included Addressables database.
2. Make sure the prefab has a root `NetworkObject`.
3. Regenerate `AssetSubSystem` data from `Project Settings/SS3D/Assets`.
4. Confirm `NetworkObjects.asset` refreshes.
5. Spawn through `NetworkSpawner.SpawnAsync(...)`.
6. Test host mode, dedicated server mode, multiple clients, and a late-joining client.

## Common mistakes

* Calling `InstanceFinder.ServerManager.Spawn(...)` directly for an addressable prefab.
* Calling `NetworkSpawner.Spawn(...)` instead of `SpawnAsync(...)` for a prefab loaded through `AssetSubSystem`.
* Spawning an already-instantiated object without passing the asset GUID or `ObjectAssetReference`.
* Forgetting to include the prefab's database in `AddressablesCatalog`.
* Forgetting to refresh generated `AssetSubSystem` data after moving prefabs between Addressables groups.
