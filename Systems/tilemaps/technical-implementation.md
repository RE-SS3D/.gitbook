---
description: This page describes some of the inner workings of the tilesystem
---

# Technical Implementation

### Setting up a new TileSystem

In order to create a new tilesystem, you need to create a new GameObject in a scene and add the following scripts:

* TileSystem
* TileResourceLoader

Furthermore in order to use the creator, you will need to add the **ConstructionMenu** prefab to the scene.

### Startup

When playing in runtime, the TileSystem will automatically try to load a saved tilemap from the StreamingAssets folder and recreate it using ScriptableObjects found by the TileResourceLoader.

## Internal structure

When placed, the tilemap uses the following structure to keep track of all tiles. Ranked in order from the lowest element to the highest:

1. PlacedItemObject - This script is attached to every itemthat is spawned on the map. Ensures spawning/despawning and is always attached to a GameObject.
2. PlacedTileObject - This script is attached to every object that is spawned on the map. Ensures spawning/despawning and holds references to any adjacency connectors. Always attached to a GameObject.
3. TileObject - This class represents a single object on a single layer and can contain one PlacedTileObject. So for each tile position in the world, there is are (_**number of layers**_) amount of TileObjects. Not attached to a GameObject.
4. TileChunk - A chunk represents a 16 by 16 grid of TileObjects for each layer (16 x 16 x num of layers). Chunks are not really used at the moment, but have to potential to benefit networking and loading for massive maps in the future. Created as a GameObject as a parent to PlacedTileObjects.
5. TileMap - Holds a dictionary of chunks filled with TileObjects and a list of PlacedItemObjects. The later are not position bound so are not part of a chunk. Created as a GameObject as a parent to chunks and items.
6. TileSystem - The system to hold TileMaps, and serves as the main interaction point to place and remove items/tiles. Only a single instance of the TileSystem can exist.

### Other parts of the system

* TileResourceLoader - Reads and holds the ScriptableObjects for each item and tile that can be placed. Used by the TileSystem to figure out what object is placed.
* Saved-X-Object - Used to hold the state of the corresponding class/struct and is serializable. Used for saving and loading.
* BuildChecker -  Used to validate combinations of placed objects and can check whether an object can be placed. For example, no objects can be build on the Turf layer if a Plenum is missing.
* SaveSystem - Generic save system that is used for saving and loading of the tilemap from and to a file. Uses the StreamingAssets folder so that builds also receive it.
* TileMapCreator - Used as an in-game editor for placing and removing tiles/items and saving/loading. Is networked so that clients are also able to work on the map.
* GhostManager - Used for construction as part of the TileMapCreator to create a "ghost" object to see where you are building.
* MultiAdjacencyConnector - Used for connecting walls and tables together. Keeps track of which neighbours it is connected to and will replace and rotate meshes accordingly.&#x20;
