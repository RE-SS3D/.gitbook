# Creating an Asset Database

Use this page when adding a new content category to `AssetSubSystem`, adding assets to an existing category, or migrating old Asset Data database assets to the catalog-based Addressables setup.

The current production path is:

```text
Addressables group
        |
        v
AddressablesDatabase
        |
        v
AddressablesCatalog
        |
        v
AssetDatabaseSettings.IncludedCatalogs
```

## Create an Addressables database

1. Create or choose an Addressables group.
   * Open `Window/Asset Management/Addressables/Groups`.
   * Mark the assets addressable and move them into the group.
2. Create the database asset.
   * Put it under `Assets/Content/Data/AssetSystem/Databases`.
   * Use `Create/SS3D/Asset Subsystem/Database/Addressables`.
   * Name the asset after the generated class you want, such as `Items`, `Sounds`, or `WorldSpaceUI`.
3. Assign the Addressables group to the database's `AssetGroup` field.
4. In the database inspector, press `Load Assets From Addressables Group`.
   * This refreshes the database's serialized GUID list.
   * This also regenerates the generated constants.
5. Make sure the database belongs to an included catalog.
   * The current catalog lives at `Assets/Content/Data/AssetSystem/Catalogs/AddressablesCatalog.asset`.
   * `Project Settings/SS3D/Assets` should include that catalog in `IncludedCatalogs`.
6. In `Project Settings/SS3D/Assets`, press `Find and load asset catalogs`.
   * The settings inspector asks each included catalog to rediscover its databases.
   * `AddressablesCatalog` discovers every `AddressablesDatabase` and refreshes each database from its Addressables group.
   * Generated constants are rewritten under `Assets/Scripts/SS3D/Data/Generated`.
   * `ObjectAssetReference` assets are created or updated for GameObject entries.
   * Prefabs are stamped with runtime asset metadata.

## Generated output

Generation writes and updates:

* asset GUID constants in `Assets/Scripts/SS3D/Data/Generated/<DatabaseName>.cs`
* database GUID constants in `Assets/Scripts/SS3D/Data/Generated/AssetDatabases.cs`
* generated object references in `Assets/Content/Data/ObjectAssetReferences`
* `AssetIdentifier` and `InstanceLifetimeTracker` stamps on GameObject assets
* `NetworkObjectTracker` stamps on root `NetworkObject` prefabs
* the generated FishNet prefab collection at `Assets/Content/Data/AssetSystem/NetworkObjects.asset`

The generated constants are GUID keys. They are not loaded assets.

## Add an asset to an existing database

1. Add the asset to the correct Addressables group.
2. Open the matching `AddressablesDatabase` asset.
3. Press `Load Assets From Addressables Group`.
4. Open `Project Settings/SS3D/Assets`.
5. Press `Find and load asset catalogs`.
6. Use the new generated constant, such as `Items.NewThing`.
7. If a designer needs to select the asset in the inspector, confirm that an `ObjectAssetReference` exists or create one with the relevant editor tool.

## Add a network prefab

Network prefabs need the normal database path plus FishNet registration.

1. Add the prefab to an Addressables group that belongs to an included `AddressablesDatabase`.
2. Make sure the prefab has a root `NetworkObject`.
3. Press `Find and load asset catalogs` in `Project Settings/SS3D/Assets`.
4. Confirm `Assets/Content/Data/AssetSystem/NetworkObjects.asset` refreshes.
5. Spawn the prefab with `NetworkSpawner.SpawnAsync(...)`, passing the generated GUID constant or `ObjectAssetReference`.

Do not use `InstanceFinder.ServerManager.Spawn(...)` directly for addressable prefabs loaded through `AssetSubSystem`. That skips the preload barrier and can let clients receive a FishNet spawn before the addressable prefab is loaded and registered.

For the full network flow, see [Networked Addressables](networked-addressables.md).

## Migrating an old database

Old Asset Data databases were direct `AssetDatabase` ScriptableObjects included through `AssetDatabaseSettings.IncludedAssetDatabases`. They stored a dictionary of GUIDs to Unity object references.

The new setup keeps the database concept, but the runtime database is lighter:

* create an `AddressablesDatabase` instead of the old concrete `AssetDatabase`
* move the asset list source of truth to the Addressables group
* let the database store GUIDs from that group
* include the database through an `AddressablesCatalog`
* include the catalog through `AssetDatabaseSettings.IncludedCatalogs`

Use `Assets/Content/Data/AssetSystem/Databases` for database assets and `Assets/Content/Data/AssetSystem/Catalogs` for catalog assets.

## Validation

Run the asset audit tests after changing catalogs, databases, Addressables groups, or prefabs. The current tests cover:

* included catalogs are present and non-empty
* included databases are present and non-empty
* every project `AssetDatabase` is reachable through an included catalog
* database GUIDs resolve to real assets
* prefabs have valid `AssetIdentifier`, `InstanceLifetimeTracker`, and `NetworkObjectTracker` stamps
* generated network prefab order is stable and GUID-based

For networked prefabs, also do a host/server/client smoke test, including a late-joining client.
