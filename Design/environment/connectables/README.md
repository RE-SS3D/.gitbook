---
description: The system for connectable tilemap objects.
cover: ../../.gitbook/assets/ProbablyNot_Reply.png
coverY: 0
---

# 🧩 Connectables

_**For technical documentation on this system use the link below.**_

{% content-ref url="https://app.gitbook.com/s/95OhrYYgKj0eUTnfM9sL/tilemaps/adding-new-items-and-objects/adjacency-connections" %}
[Adjacency Connections](https://app.gitbook.com/s/95OhrYYgKj0eUTnfM9sL/tilemaps/adding-new-items-and-objects/adjacency-connections)
{% endcontent-ref %}

Connectables are a sub-system of [Tilemaps](../tilemaps/) which use adjacency connection scripts to replace models depending on the status of neighboring tiles.

This works by using several differently shaped models and replacing them depending on any adjacent tiles with the same type of connectable (see the Tilemap document for more details).

Different types of connectables have different ways they allow or don’t allow connections.

<figure><img src="https://lh5.googleusercontent.com/c3FRK_ZKQYLnXBhkpp4tCj7k9Kn4HWWi-1WfbzkofsYekS330dtCG476bOM1e56bmQc5iXidDz1g9G3hlTdXXeHToUcItnjUuClXmRE1UvvZNOtizzaG6PsmLRzxtnCz9YYfAOpPYs1Ux62iVRt5tg" alt=""><figcaption><p>For example, wires can connect diagonally and have several unique shapes that are not possible with tables.</p></figcaption></figure>

As a result, we use several unique mathematical scripts known as “adjacency connectors” to handle the connection logistics.

Types of connectables are manually defined by an ID known as a “generic type” (ex. wall, table, wire, cable, etc.). When properly assigned, this ID makes sure different types of connectables properly connect to themselves but not other types of connectables.

In addition to generic types, some connectables may even have a “specific type” ID. The specific type is used to distinguish different variants of the same type of connectable. The best example is having multiple material-based table variants (wood & metal), the specific type could be used to prevent connections between different variant types while maintaining connections between the same variant types.

It should also be noted that objects will only connect if they are connected to the tilemap, removing them from the tilemap will disconnect any connections to it. Some objects can be bolted to / unbolted from the tilemap (tables, girders, sofa, etc.), while others also have ways to be attached / detached to the tilemap.
