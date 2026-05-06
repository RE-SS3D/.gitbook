# Troubleshooting and Known Issues

`AssetSubSystem` makes runtime loading explicit. Most problems come from treating a GUID as a loaded asset, losing a handle, or bypassing the network preload path.

## Handles must be released

Every successful `AssetRequest<T>.LoadAsync()` returns an `AssetHandle<T>` that must be disposed. A leaked handle keeps the asset loaded. In editor and development builds, undisposed handles log a warning when finalized.

Use one of these patterns:

* `handle.Dispose()` when manually managing a local load
* `AssetHandle.Release(ref _handle)` for stored fields
* `handle.TieLifetimeTo(this)` when a component should own the handle until its GameObject is destroyed

## Generated constants are IDs only

`Items.PDA`, `Sounds.BikeHorn`, and similar generated members are GUID strings. They do not contain the asset and they do not load anything by themselves.

Replace old `Assets.Get<T>(...)` usage with `AssetRequest<T>` and read `handle.Asset` only after checking that the handle is valid.

## AssetSubSystem must be initialized

`AssetRequest<T>.LoadAsync()` returns `null` if `AssetSubSystem` is missing or not initialized. Avoid asset requests before application startup initializes subsystems, and make sure the boot scene contains a configured `AssetSubSystem`.

## Catalog inclusion matters

`ObjectAssetReference` no longer stores a database ID. The subsystem finds the owning database by scanning included catalogs. If an asset is in an Addressables group but that group's `AddressablesDatabase` is not reachable through an included catalog, loads by generated constant and `ObjectAssetReference` will fail.

Use `Project Settings/SS3D/Assets` and press `Find and load asset catalogs` after changing database or catalog assets.

## Database renames can leave stale generated files

Generation writes a new class for the current database asset name, but it does not automatically delete every old generated file from a previous name. If a database is renamed, check `Assets/Scripts/SS3D/Data/Generated` for stale classes.

## ObjectAssetReference auto-generation is limited

The generator creates `ObjectAssetReference` assets for GameObject entries in asset databases. Other asset types can still be referenced if an editor tool creates an `ObjectAssetReference` for them and the GUID belongs to an included database. Audio clips currently use this path.

If a reference exists but loading fails, check that the referenced GUID is still present in an included catalog.

## Direct FishNet spawning can race Addressables

`NetworkSpawner.Spawn(...)` is only a FishNet wrapper for objects already known to every client. It does not synchronize Addressables.

Use `NetworkSpawner.SpawnAsync(...)` for prefabs loaded through `AssetSubSystem`. This waits for `NetworkBarrier`, registers late-join state, and keeps clients from observing objects before their addressable prefabs are loaded.

## File backend is not implemented

`AssetBackendType` includes `File`, but the current implementation includes Addressables and Resources backends. Do not create a catalog that routes to `File` until a matching backend exists.

## Runtime fallback stamps are not a migration strategy

`AssetLifecycleTracker` and `NetworkSpawner` can add an `InstanceLifetimeTracker` at runtime if a loaded prefab is missing one. That is a compatibility fallback. The prefab should still be regenerated or stamped so audit tests pass and runtime behavior is deterministic.

## Manual network validation is still required

The automated tests cover handles, provider deduplication, lifecycle tracking, prefab stamping, catalog inclusion, and NetworkObjects generation. They do not replace manual host/server/client validation for:

* item spawning
* tile placement and map loading
* crafting outputs
* role loadouts
* audio and interaction icons
* late-joining clients observing addressable network prefabs
