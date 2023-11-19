# Adding new items & objects

### Creating ScriptableObjects

To add a new item or object to the tilemap system, a new scriptableobject needs to be created.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Right click in the Unity Editor to create a new object</p></figcaption></figure>

### Location

Make sure to save the item/tile ScriptableObjects under the corresponding "Content/Data/TileMap/Resources/" folder

### Details

The following information can be filled in for a TileObjectSo:

#### Tile objects

* Name String - describes the name of the object
* Prefab - which prefab to spawn
* Icon - Icon which is used by the creator and construction interface
* Layer - which layer the item should be put in
* Generic Type - Generics types are used to categorize objects on the same layer. Used by the adjacency connector to connect walls for example
* Specific Type - Specific types are used to specify the material that the object is made of. For example used by carpets to ensure that they don't connect to other floors&#x20;
* Width - width of the object. Used for multi-tile objects
* Height - height of the object. Used for multi-tile objects

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Details to fill in</p></figcaption></figure>

#### Items

Items can be added in a similar way:

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption><p>Items follow the same approach</p></figcaption></figure>

{% hint style="warning" %}
Make sure the Name String is unique. Not doing so will create issues during loading & saving.
{% endhint %}
