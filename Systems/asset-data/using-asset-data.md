---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Using AssetSubSystem

`AssetSubSystem` is used from gameplay code through `AssetRequest<T>` and `AssetHandle<T>`.

Generated database classes live in `Assets/Scripts/SS3D/Data/Generated`. Their members are GUID strings. A GUID becomes a loaded asset only after it is requested through the subsystem.

For old-to-new examples, see [Migrating From Asset Data](migration-from-asset-data.md). For ownership details, see [Handles and Lifetime](handles-and-lifetime.md).

## Rules of thumb

* Use `new AssetRequest<T>(id).LoadAsync()` for generated GUID constants.
* Use `new AssetRequest<T>(reference).LoadAsync()` for `ObjectAssetReference` fields.
* Check the returned handle before reading `handle.Asset`.
* Dispose every successful handle, or bind it to an owner with `TieLifetimeTo`.
* Keep handles in fields when the asset is reused across frames.
* Use `NetworkSpawner.SpawnAsync(...)` for addressable network prefabs.
* Use `NetworkSpawner.Spawn(...)` only for objects already known to every client without `AssetSubSystem` synchronization.

## Load a generated asset

```csharp
using SS3D.Data;
using SS3D.Data.Generated;
using UnityEngine;

AssetHandle<AudioClip> clipHandle = await new AssetRequest<AudioClip>(Sounds.BikeHorn).LoadAsync();

if (!clipHandle)
{
    clipHandle?.Dispose();
    return;
}

AudioClip clip = clipHandle.Asset;

// Use the clip while the handle is alive.

clipHandle.Dispose();
```

Common generated IDs include:

* `Items.PDA`
* `InteractionIcons.Open`
* `Materials.ValidConstruction`
* `ParticlesEffects.BleedingParticle`
* `Sounds.BikeHorn`
* `WorldSpaceUI.LoadingBar`

## Load a component from a prefab

If the loaded asset is a `GameObject` and `T` is a component type, `AssetProvider` returns that component from the prefab. This is how migrated systems request items, body parts, UI prefabs, recipes, and effects.

```csharp
using SS3D.Data;
using SS3D.Data.Generated;
using SS3D.Data.Networking;
using SS3D.Systems.Inventory.Items;
using UnityEngine;

AssetHandle<Item> itemHandle = await new AssetRequest<Item>(Items.BikeHorn).LoadAsync();

if (!itemHandle)
{
    itemHandle?.Dispose();
    return;
}

Item itemPrefab = itemHandle.Asset;

// Use the prefab while the handle is alive.
itemHandle.Dispose();
```

For networked prefabs, instantiate and spawn before releasing the handle:

```csharp
Item itemInstance = Object.Instantiate(itemHandle.Asset, position, rotation);
await NetworkSpawner.SpawnAsync(itemInstance, Items.BikeHorn);
itemHandle.Dispose();
```

The spawned instance keeps the asset resident through `InstanceLifetimeTracker`.

## Keep a long-lived handle

Icons, looping clips, construction materials, and cached UI prefabs should keep handles for as long as their owner uses the asset.

```csharp
using SS3D.Data;
using SS3D.Data.Generated;
using UnityEngine;

public sealed class OpenIconOwner : MonoBehaviour
{
    private AssetHandle<Sprite> _openIconHandle;

    private async void Awake()
    {
        _openIconHandle = await new AssetRequest<Sprite>(InteractionIcons.Open).LoadAsync();

        if (!_openIconHandle)
        {
            AssetHandle.Release(ref _openIconHandle);
        }
    }

    private void OnDestroy()
    {
        AssetHandle.Release(ref _openIconHandle);
    }

    public Sprite GetIcon()
    {
        return _openIconHandle ? _openIconHandle.Asset : null;
    }
}
```

`AssetHandle.Release(ref handle)` disposes the handle and clears the field. This avoids accidental reuse after release.

You can also bind a handle to a `Component`:

```csharp
AssetHandle<Sprite> handle = await new AssetRequest<Sprite>(InteractionIcons.Open).LoadAsync();

if (handle)
{
    handle.TieLifetimeTo(this);
}
```

This adds a hidden `HandleGuard` to the owner's GameObject and releases the handle when that GameObject is destroyed.

## Use ObjectAssetReference

Use `ObjectAssetReference` when the asset should be selected in the inspector. The generated references live in `Assets/Content/Data/ObjectAssetReferences`.

```csharp
using SS3D.Data;
using SS3D.Data.AssetDatabases;
using SS3D.Data.Networking;
using System.Threading.Tasks;
using UnityEngine;

public sealed class ObjectSpawner : MonoBehaviour
{
    [SerializeField]
    private ObjectAssetReference _prefabAsset;

    public async Task<GameObject> SpawnAsync()
    {
        AssetHandle<GameObject> handle = await new AssetRequest<GameObject>(_prefabAsset).LoadAsync();

        if (!handle)
        {
            handle?.Dispose();
            return null;
        }

        GameObject instance = Object.Instantiate(handle.Asset);
        await NetworkSpawner.SpawnAsync(instance, _prefabAsset);
        handle.Dispose();

        return instance;
    }
}
```

`ObjectAssetReference.Id` is the GUID passed to the subsystem. The reference no longer stores a database name.

## Read database contents

`AssetSubSystem.GetDatabase(...)` returns a database by generated database GUID. This is useful when a system needs all assets in a category, such as crafting recipes.

```csharp
using Coimbra;
using SS3D.Data;
using SS3D.Data.AssetDatabases;
using SS3D.Data.Generated;
using SS3D.Systems.Crafting;

AssetSubSystem assetSubSystem = SubSystems.Get<AssetSubSystem>();
AssetDatabase recipesDatabase = assetSubSystem.GetDatabase(AssetDatabases.CraftingRecipes);

foreach (string recipeGuid in recipesDatabase.AssetGuids)
{
    AssetHandle<CraftingRecipe> recipeHandle = await new AssetRequest<CraftingRecipe>(recipeGuid).LoadAsync();
}
```

The database gives you GUIDs. It does not contain loaded Unity object references.

## Failure cases

`LoadAsync()` can return `null` or an invalid handle when:

* `AssetSubSystem` is missing or has not initialized
* no included catalog contains the GUID
* the backend cannot load the asset
* the requested component type is not present on a loaded `GameObject`

Always check the handle, and dispose it if one was returned.
