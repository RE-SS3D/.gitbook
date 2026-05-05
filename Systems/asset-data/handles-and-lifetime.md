# Handles and Lifetime

The old Asset Data system kept loaded objects in database assets. `AssetSubSystem` instead keeps assets resident while there is an owner for them. Ownership comes from two places:

* live `AssetHandle<T>` instances
* live prefab instances tracked by `InstanceLifetimeTracker`

When both counts reach zero for a GUID, the provider unloads the asset through the backend that loaded it.

## Handle ownership

`AssetRequest<T>.LoadAsync()` returns an `AssetHandle<T>`. A valid handle contributes one reference to the loaded asset. Disposing that handle releases the reference.

```csharp
AssetHandle<GameObject> handle = await new AssetRequest<GameObject>(Items.BikeHorn).LoadAsync();

if (!handle)
{
    handle?.Dispose();
    return;
}

GameObject prefab = handle.Asset;
handle.Dispose();
```

For fields, prefer `AssetHandle.Release(ref _handle)`. It disposes the handle and sets the field to `null`.

```csharp
private AssetHandle<Sprite> _iconHandle;

private void OnDestroy()
{
    AssetHandle.Release(ref _iconHandle);
}
```

In editor and development builds, an undisposed handle logs a warning when finalized. Treat that warning as a leak.

## Long-lived handles

Keep a handle alive when a component repeatedly uses a loaded asset. Examples from the migrated code include interaction icons, impact sounds, airlock sounds, construction materials, recipe assets, and the client loading bar prefab.

You can bind a handle to a component owner:

```csharp
AssetHandle<Sprite> handle = await new AssetRequest<Sprite>(InteractionIcons.Open).LoadAsync();

if (handle)
{
    handle.TieLifetimeTo(this);
}
```

`TieLifetimeTo` adds a hidden `HandleGuard` to the owner's GameObject. The guard disposes tracked handles when that GameObject is destroyed.

## Prefab instance tracking

GameObject assets that participate in `AssetSubSystem` are stamped by editor generation with:

* `AssetIdentifier`, which stores the prefab GUID
* `InstanceLifetimeTracker`, which tracks instantiated copies

When the backend loads a GameObject asset, `AssetLifecycleTracker` arms its `InstanceLifetimeTracker`. When Unity instantiates a copy, the copy announces itself and adds a reference count. When that copy is destroyed, the reference is released.

This means a temporary prefab load handle can be released after the prefab is instantiated and, for networked objects, after `NetworkSpawner.SpawnAsync(...)` has tracked the spawned instance.

```csharp
AssetHandle<GameObject> handle = await new AssetRequest<GameObject>(Items.BikeHorn).LoadAsync();

if (!handle)
{
    handle?.Dispose();
    return;
}

GameObject instance = Object.Instantiate(handle.Asset);
handle.Dispose();
```

The instance keeps the asset resident until it is destroyed, assuming the prefab has a valid `InstanceLifetimeTracker` stamp. The audit tests verify these stamps.

## Networked instances

For networked prefabs, use `NetworkSpawner.SpawnAsync(...)` rather than direct FishNet spawning.

```csharp
NetworkObject spawned = await NetworkSpawner.SpawnAsync(Items.BikeHorn);
```

If another system already instantiated the object, pass the same asset key or `ObjectAssetReference` when spawning:

```csharp
GameObject instance = Object.Instantiate(handle.Asset);
await NetworkSpawner.SpawnAsync(instance, Items.BikeHorn);
handle.Dispose();
```

`NetworkSpawner` waits for client preload, spawns through FishNet, initializes instance lifetime tracking, and registers active network instances for late joiners.

## What unloads an asset

An asset unloads when all of these are true:

* every `AssetHandle<T>` for the GUID has been disposed
* every tracked prefab instance for the GUID has been destroyed
* every active network instance for the GUID has been released from the world

`AddressablesBackend` then releases the Addressables operation handle. `ResourcesBackend` unloads non-GameObject assets.

## Failure handling

Always check the handle before reading `handle.Asset`. A request can fail when:

* `AssetSubSystem` is not initialized
* no included catalog contains the GUID
* no backend is registered for the owning catalog type
* the backend fails to load the asset
* the requested component type is missing on a loaded `GameObject`

When a load fails, dispose the handle if one was returned.
