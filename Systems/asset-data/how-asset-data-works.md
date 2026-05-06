# How AssetSubSystem Works

`AssetSubSystem` has three jobs:

* map generated GUIDs and `ObjectAssetReference` assets to real Unity assets
* keep loaded assets alive only while something still needs them
* make addressable network prefabs available on clients before the server spawns them

For caller-facing lifetime rules, see [Handles and Lifetime](handles-and-lifetime.md). For FishNet-specific behavior, see [Networked Addressables](networked-addressables.md).

## From old flow to new flow

The old flow was:

```text
Generated GUID + database GUID
        |
        v
Assets.Get<T>(databaseId, assetId)
        |
        v
static Assets database dictionary
        |
        v
AssetDatabase.Assets[assetId]
        |
        v
Unity object reference
```

The new flow is:

```text
Generated GUID or ObjectAssetReference
        |
        v
AssetRequest<T>.LoadAsync()
        |
        v
AssetSubSystem.AcquireAsync<T>(guid)
        |
        v
AssetCatalog finds the database that owns the GUID
        |
        v
IAssetBackend loads the resolved key
        |
        v
AssetProvider returns AssetHandle<T>
```

The generated constants did not disappear. The static runtime cache did. The subsystem now resolves a GUID through catalogs and loads it on demand.

## Startup

`AssetSubSystem` is a scene-owned `SubSystem`. During `ApplicationInitializing`, it:

1. reads `AssetDatabaseSettings.IncludedCatalogs`
2. creates one backend per distinct catalog backend type
3. initializes each backend
4. indexes every included database by `DatabaseID`
5. creates the shared `AssetProvider` and `AssetLifecycleTracker`
6. spawns the `NetworkBarrier` after the server starts

The configured Addressables chain is:

1. `AssetDatabaseSettings` includes `AddressablesCatalog`.
2. `AddressablesCatalog` owns the Addressables databases.
3. Each `AddressablesDatabase` stores asset GUIDs from one Addressables group.
4. `AddressablesBackend` loads assets by GUID.

The currently configured Addressables databases are:

* `CraftingRecipes`
* `InteractionIcons`
* `Items`
* `Materials`
* `ParticlesEffects`
* `Sounds`
* `WorldSpaceUI`

## Catalogs and databases

`AssetCatalog` groups databases that share a backend. It answers "does this catalog contain this GUID?", resolves the backend-specific key, and creates the backend implementation.

`AddressablesCatalog` routes to `AssetBackendType.Addressables` and creates `AddressablesBackend`.

`AssetDatabase` is the base ScriptableObject for database assets. Each concrete database exposes `AssetGuids`, checks whether it has a GUID, and resolves a GUID to a backend key.

`AddressablesDatabase` stores a list of GUIDs loaded from an Addressables group. Its `ResolveKey` returns the GUID itself because Addressables can load by GUID.

`AssetDatabaseSettings` stores included catalogs, not a flat database list. Its `AllDatabases` view flattens the catalog databases for generator and audit code.

## Backends

Backends implement `IAssetBackend`:

* `InitializeAsync()`
* `LoadAsync(guid, resolvedKey)`
* `Unload(guid, resolvedKey)`
* `OnLoaded`
* `OnUnloaded`

`AddressablesBackend` is the only runtime asset subsystem file that references `UnityEngine.AddressableAssets`. It initializes Addressables, calls `Addressables.LoadAssetAsync<Object>(resolvedKey)`, stores operation handles by GUID, and releases them on unload.

`ResourcesBackend` exists for `Resources.LoadAsync` paths. It unloads non-GameObject assets through `Resources.UnloadAsset`.

`AssetBackendType.File` exists in the enum, but there is no matching file backend implementation yet.

## Provider and casting

`AssetProvider` owns loaded asset records. It deduplicates concurrent requests, so two systems asking for the same GUID share the same backend load task.

When a requested type is not `GameObject` and the loaded asset is a `GameObject`, the provider tries `GetComponent<T>()`. This lets code request components from prefabs:

```csharp
AssetHandle<Item> itemHandle = await new AssetRequest<Item>(Items.BikeHorn).LoadAsync();
```

If the component is not present, the handle is invalid.

## Runtime ownership

`AssetLifecycleTracker` is the unload decision-maker. `AssetSubSystem` calls `TrackAcquire(guid)` before awaiting the provider. `AssetHandle<T>.Dispose()` calls back into the tracker to release that handle reference.

For GameObject assets, the tracker also listens for loaded assets and arms their `InstanceLifetimeTracker`. Instantiated copies announce themselves and add an instance reference; destroying those copies releases the instance reference.

The backend unloads only after handle references and instance references are both gone.

## Generated code

Generation writes constants to `Assets/Scripts/SS3D/Data/Generated`.

Per-database generated classes contain asset GUID constants:

```csharp
public static class Items
{
    public const string BikeHorn = "11f824c472e04854e95065dda095e8f4";
}
```

The generated `AssetDatabases` class contains database GUID constants:

```csharp
public static class AssetDatabases
{
    public const string Items = "c2644d7b34e956743a0bc485e7ca5e37";
}
```

These constants are stable lookup IDs. They do not load assets.

## Object asset references

`ObjectAssetReference` assets live in `Assets/Content/Data/ObjectAssetReferences`.

The old reference stored both asset GUID and database GUID. The new reference stores only:

```csharp
public string Id;
```

`AssetRequest<T>(ObjectAssetReference reference)` loads `reference.Id`. The owning database is resolved through included catalogs.

The generator creates and updates references for GameObject entries in databases. Editor tooling can also create references for other included assets, such as audio clips.

## Prefab stamping

`AssetPrefabStamper` applies the metadata required by runtime loading:

* `AssetIdentifier` stores the asset GUID.
* `InstanceLifetimeTracker` tracks instantiated copies.
* `NetworkObjectTracker` is added only to prefabs with a root `NetworkObject`.

The prefab audit tests verify the stamps. Runtime fallbacks exist for missing trackers, but a missing stamp should be treated as migration debt.

## Networked Addressables

`NetworkObjects` is a generated FishNet prefab collection backed by GUID order. Addressable prefab slots are empty until a prefab is loaded. When `AddressablesBackend` loads a network prefab, `NetworkObjectTracker` lets `NetworkObjects` place it into the correct runtime slot.

`NetworkBarrier` coordinates server and client loading before addressable spawns. `NetworkSpawner.SpawnAsync(...)` is the public entry point: it loads or validates the asset key, waits on the barrier, spawns through FishNet, tracks the network instance, and releases temporary handles at the right time.
