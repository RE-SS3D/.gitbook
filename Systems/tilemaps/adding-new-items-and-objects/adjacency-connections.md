# Adjacency Connections

_**The design of the system can be found in the the link below.**_

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

Adjacency connections refers to when a tilemap object is connectable to its neighbors, walls being the typical example of this.

## Adjacency Connectors

In order to make walls and tables connect to each other, you need to make use of a adjacency connector. This keeps track of which neighbours it is connected to and will replace and rotate meshes accordingly.

### The different adjacency connectors

&#x20;There are different types of adjacencies supported right now.

1. Simple - Used for simple connections without a lot of use cases. Covers the basic shapes such as I, U, O, T and X.&#x20;
2. Advanced - Expansion of the Simple type with a lot more edge cases covered.
3. Offset - Used for meshes which are not placed in the middle (thus offset). Used by pipes for example.
4. Disposal Furniture - checks if connected from above to a disposal pipe. Very specific one.
5. Disposal Pipe - Used for disposal pipes only.
6. Door - Specific to doors, because of the specific way it connects to other doors and to walls.
7. Pipe - For pipes with an offset (not centered on the tile)

### Implementing an adjacency connector

The first thing you need is to implement the **IAdjacencyConnector** interface.

If your tile object connects only with things from the same layer, adjacent to it, you might want to look at the **AbstractHorizontalConnector class** and inherit from it.&#x20;

It will only ask you to implement the IsConnected() method, as it varies a lot from one connector to another. Door, simple, advanced, offset, pipe all inherits from it. Chances your connector could too.

If the connections are weirder, such as disposal pipes able to connect to disposal furniture, a different object on a different layer, with a different connector, and with special behavior when it connects, then directly implement the  **IAdjacencyConnector** interface.

### Make a tile object connectable

Add the right adjacency connector script to your **prefab's root game object**. You can recognise a Connector script because it implements the **IAdjacencyConnector** interface. To know which specific script to use, check the connectables design pages.

Connectable scripts usually ask you to add specific mesh for specific configurations. You need to fill them all up for the connector to work properly.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption><p>A wall adjacency connector</p></figcaption></figure>

Check the Connectables design page for more informations about your specific connector and how the meshes should look.

Also know that the connectables scripts assume the mesh you link are rotated in a specific fashion, otherwise they may appear incorrectly in game. If you have this issue of meshes badly rotated, try to rotate the models you use, out of the game.
