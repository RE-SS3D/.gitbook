# Migrating From Asset Data

This page maps the legacy Asset Data system on `develop` to the `AssetSubSystem` flow introduced by the dynamic Addressables refactor.

The short version: keep generated GUID constants and `ObjectAssetReference` inspector assets, but stop resolving them with the static `Assets` class. Load through `AssetRequest<T>`, keep the returned `AssetHandle<T>` for as long as the asset is needed, and use `NetworkSpawner.SpawnAsync(...)` for addressable network prefabs.

## Runtime lookup

Old code looked up already-loaded objects from a database:

```csharp
Sprite icon = Assets.Get<Sprite>(AssetDatabases.InteractionIcons, InteractionIcons.Open);
GameObject prefab = Assets.Get<GameObject>(objectAssetReference);
```

New code requests assets asynchronously:

```csharp
AssetHandle<Sprite> iconHandle = await new AssetRequest<Sprite>(InteractionIcons.Open).LoadAsync();
AssetHandle<GameObject> prefabHandle = await new AssetRequest<GameObject>(objectAssetReference).LoadAsync();
```

Check the handle before reading `handle.Asset`, and dispose it when the owner no longer needs the asset.

## Database access

Old database access:

```csharp
AssetDatabase recipesDatabase = Assets.GetDatabase(AssetDatabases.CraftingRecipes);
```

New database access goes through the scene subsystem:

```csharp
AssetSubSystem assetSubSystem = SubSystems.Get<AssetSubSystem>();
AssetDatabase recipesDatabase = assetSubSystem.GetDatabase(AssetDatabases.CraftingRecipes);
```

The returned database is now a GUID database, not a dictionary of loaded Unity objects. To load each entry, iterate `AssetGuids` and request each GUID:

```csharp
foreach (string guid in recipesDatabase.AssetGuids)
{
    AssetHandle<CraftingRecipe> recipeHandle = await new AssetRequest<CraftingRecipe>(guid).LoadAsync();
}
```

## Generated constants

Generated database classes still contain constants like this:

```csharp
public static class Items
{
    public const string BikeHorn = "11f824c472e04854e95065dda095e8f4";
}
```

The difference is that gameplay code now treats these constants only as GUID keys. A generated member does not load anything by itself and does not imply the Addressables handle is alive.

## ObjectAssetReference

Old `ObjectAssetReference` assets stored:

```csharp
public string Id;
public string Database;
```

New `ObjectAssetReference` assets store only:

```csharp
public string Id;
```

That `Id` is the asset GUID. The owning database is resolved by scanning included catalogs. This is why moved assets must remain in an included `AddressablesDatabase`, and why `Project Settings/SS3D/Assets` must include the catalog that owns that database.

## Spawning prefabs

Old item and tile spawning often loaded a prefab synchronously, instantiated it, then spawned it through FishNet:

```csharp
Item itemPrefab = Assets.Get<Item>(AssetDatabases.Items, itemId);
Item itemInstance = Instantiate(itemPrefab, position, rotation);
InstanceFinder.ServerManager.Spawn(itemInstance.gameObject);
```

New code loads the prefab as a handle and uses the asset key when spawning:

```csharp
AssetHandle<Item> itemHandle = await new AssetRequest<Item>(itemId).LoadAsync();

if (!itemHandle)
{
    itemHandle?.Dispose();
    return null;
}

Item itemInstance = Instantiate(itemHandle.Asset, position, rotation);
await NetworkSpawner.SpawnAsync(itemInstance, itemId);
itemHandle.Dispose();
```

`NetworkSpawner.SpawnAsync(...)` waits for `NetworkBarrier` to make clients load the prefab before FishNet receives the spawn. Use the non-async `NetworkSpawner.Spawn(...)` path only for objects that are already available on every client without addressable synchronization.

## Editor data

Old setup:

* database assets lived under the old database folder
* `AssetDatabaseSettings.IncludedAssetDatabases` held every database directly
* each database serialized loaded Unity object references in `Assets`
* the settings inspector button was `Find and load asset databases`

New setup:

* database assets live under `Assets/Content/Data/AssetSystem/Databases`
* catalogs live under `Assets/Content/Data/AssetSystem/Catalogs`
* `AssetDatabaseSettings.IncludedCatalogs` holds catalogs, not databases
* `AddressablesDatabase` stores asset GUIDs from an Addressables group
* the settings inspector button is `Find and load asset catalogs`

Generation now updates the generated GUID constants, object asset references, and prefab stamps used by runtime lifecycle tracking. Network prefabs also update the generated `NetworkObjects.asset`.

## Migration checklist

1. Replace `Assets.Get<T>(...)` with `await new AssetRequest<T>(...).LoadAsync()`.
2. Store every successful `AssetHandle<T>` until the asset is no longer needed.
3. Replace `Assets.GetDatabase(...)` with `SubSystems.Get<AssetSubSystem>().GetDatabase(...)`.
4. Replace direct FishNet spawning of addressable prefabs with `NetworkSpawner.SpawnAsync(...)`.
5. Regenerate from `Project Settings/SS3D/Assets` after moving assets, changing Addressables groups, or adding databases.
6. Run the asset audit tests and do a host/server/client smoke test for networked prefabs.
