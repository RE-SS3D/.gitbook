---
description: The runtime asset loading and database system.
cover: ../.gitbook/assets/ProbablyNot_Chase.png
coverY: 0
---

# AssetSubSystem

`AssetSubSystem` is SS3D's runtime asset loading layer. It replaces the old static `Assets` lookup flow with async GUID-based loading, backend catalogs, disposable handles, prefab lifetime tracking, and FishNet-safe addressable spawning.

The generated classes in `SS3D.Data.Generated`, such as `Items`, `Sounds`, `InteractionIcons`, and `WorldSpaceUI`, still expose string GUID constants. The important change is how those GUIDs are used: code now passes them to `AssetRequest<T>` and receives an `AssetHandle<T>` that keeps the loaded asset resident until the handle, and any tracked instances, are released.

## What changed

| Legacy Asset Data | AssetSubSystem |
| --- | --- |
| `Assets.Get<T>(databaseId, assetId)` synchronously returned a loaded object from a serialized database dictionary. | `await new AssetRequest<T>(assetId).LoadAsync()` asynchronously loads through the owning catalog/backend and returns an `AssetHandle<T>`. |
| `AssetDatabaseSettings.IncludedAssetDatabases` was a flat list of databases. | `AssetDatabaseSettings.IncludedCatalogs` contains catalogs. Each catalog owns databases and selects a backend. |
| `AssetDatabase` stored `SerializableDictionary<string, Object>` entries. | `AssetDatabase` is abstract and stores or resolves GUIDs. `AddressablesDatabase` stores GUIDs from an Addressables group and resolves the GUID as the Addressables key. |
| `ObjectAssetReference` stored both `Id` and `Database`. | `ObjectAssetReference` stores only `Id`, the asset GUID. The database is found through catalogs. |
| Addressables existed behind the old database assets, but gameplay code still read already-loaded Unity object references. | Addressables is now the runtime backend. `AddressablesBackend` loads by GUID and `AssetProvider` deduplicates concurrent requests. |
| Networked prefabs were spawned through normal FishNet paths once code had a prefab reference. | Addressable network prefabs go through `NetworkSpawner.SpawnAsync(...)`, `NetworkBarrier`, and the generated `NetworkObjects` collection so clients preload before spawn messages arrive. |
| Prefabs did not carry runtime asset identity consistently. | Generated/migrated prefabs are stamped with `AssetIdentifier`, `InstanceLifetimeTracker`, and, for network prefabs, `NetworkObjectTracker`. |

## Where to start

* [Using AssetSubSystem](using-asset-data.md) covers the day-to-day API: load requests, handles, generated IDs, object references, and spawn calls.
* [Migrating From Asset Data](migration-from-asset-data.md) compares old `Assets.Get(...)` usage with the new async patterns.
* [Creating an Asset Database](creating-an-asset-database.md) covers Addressables groups, database assets, catalog refresh, generated code, and validation.
* [Handles and Lifetime](handles-and-lifetime.md) explains handle ownership, prefab instance tracking, and when assets unload.
* [Networked Addressables](networked-addressables.md) explains FishNet prefab registration, preload barriers, and late join handling.
* [How AssetSubSystem Works](how-asset-data-works.md) gives the internal architecture for maintainers.
* [Known Issues](known-issues.md) lists sharp edges and migration notes.

## What it is for

Use `AssetSubSystem` when code needs project content without serializing direct prefab, sprite, material, audio, or ScriptableObject references everywhere. The configured backend is Addressables, but the catalog/backend split lets the subsystem route other backends through the same request API.

Use it for:

* item, tile object, furniture, VFX, UI, audio, material, and recipe lookups
* content selected from generated database constants
* content selected in the inspector through `ObjectAssetReference`
* networked prefab spawning that must wait until clients have loaded addressable prefabs

Generated constants are IDs only. They are not loaded assets and they do not keep bundles resident.

## Main pieces

* `AssetSubSystem` is the scene-owned composition root. It initializes catalogs and backends at application startup, owns the shared `AssetProvider`, and exposes the network preload barrier.
* `AssetCatalog` groups databases that share a backend. The configured catalog is `AddressablesCatalog`.
* `AssetDatabase` stores GUIDs for one content category. The configured Addressables databases are `CraftingRecipes`, `InteractionIcons`, `Items`, `Materials`, `ParticlesEffects`, `Sounds`, and `WorldSpaceUI`.
* `AssetRequest<T>` is the public load request builder. It accepts a GUID string or an `ObjectAssetReference`.
* `AssetHandle<T>` keeps the loaded asset resident while it is alive. Dispose it when the caller no longer needs the asset.
* `ObjectAssetReference` is a ScriptableObject for inspector fields. The generator creates these for GameObject assets, and editor tools can create them for other included assets. It stores only the asset GUID.
* `NetworkSpawner`, `NetworkBarrier`, and `NetworkObjects` handle FishNet spawning for addressable network prefabs.

## Project locations

* Catalogs: `Assets/Content/Data/AssetSystem/Catalogs`
* Databases: `Assets/Content/Data/AssetSystem/Databases`
* Object asset references: `Assets/Content/Data/ObjectAssetReferences`
* Generated constants: `Assets/Scripts/SS3D/Data/Generated`
* Generated FishNet prefab collection: `Assets/Content/Data/AssetSystem/NetworkObjects.asset`
* Settings: `Project Settings/SS3D/Assets`

## Basic example

```csharp
using SS3D.Data;
using SS3D.Data.Generated;
using SS3D.Data.Networking;
using SS3D.Systems.Inventory.Items;
using UnityEngine;

AssetHandle<Item> handle = await new AssetRequest<Item>(Items.BikeHorn).LoadAsync();

if (!handle)
{
    handle?.Dispose();
    return;
}

Item bikeHorn = Object.Instantiate(handle.Asset);
await NetworkSpawner.SpawnAsync(bikeHorn, Items.BikeHorn);
handle.Dispose();
```

If the object is networked and loaded through `AssetSubSystem`, prefer `NetworkSpawner.SpawnAsync(...)` so clients preload the backing prefab before FishNet spawns it.
