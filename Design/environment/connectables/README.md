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

## Basic Adjacency Connections

Basic connections use the “Basic Adjacency Connector” script and are ultimately the simplest connection type.

These basic shapes are defined below:

O - A variant with no connections.

U - A variant with 1 connection, to the north.

I - A variant with 2 connections opposite of each other, 1 to the north and 1 to the south.

L - A variant with 2 connections adjacent to each other, 1 to the north, and 1 to the east.

T - A variant shaped like a “T”, with 3 connections, 1 to the south, east, and west.

X - A variant shaped like a “+”, with 4 connections, 1 to the north, east, south, & west.

<figure><img src="https://lh6.googleusercontent.com/QFMBc2sWpPtPXLGSYvUztlUSNFJgyOtlx9wozrQ-JB41-92pIE6OJ0BG_gkeZjFSDuf46CYfwSsCKGGbxTBrOUx8AuuOX1sTFCEiDnx_sSMrFYg30PQ6B-I-X5xL4sIPBGkipM44snyTp0EpJIJL8Q" alt=""><figcaption><p>The basic adjacency shapes for pipes (left) and tables (right)</p></figcaption></figure>

These pieces can be rotated to create many various shapes. This works fine for objects that do not have corner connections (pipes, cables, etc.), but this won’t suffice for objects that do (tables, walls, etc.) because it will leave gaps where the corners meet.

<figure><img src="https://lh4.googleusercontent.com/J0YkeTKiqnnBoEuoXywe0Puyrbh6Jgf14zomHn3JqGMXuBqU1er-ObXl_XJxLMHOusGoinsQDmYyUwLmHy084ym9JLtSHXjHJJmr4DLbBzCOjFjcnmAIFQCOFWWo6G_XDxpkfOrzrQJC5bz2gkqJ9g" alt=""><figcaption><p>An example of connected pipes and tables.</p></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/BkhUBDKy8cE1exvaHZ5aKXSJPzAT5DE1KO_JFDfOFnQhtlG0w2TdzlgdwJb3ITJ6_dNoUDqXXXTA6lFaO7vNLjYld5vIws6i33Tpxmwy8SMAtyic7eLRAxP9qKh3BuFO4F21hZCIQzIutw95vYWeyA" alt=""><figcaption><p>The same connected table with indicators of the type of the connectables.</p></figcaption></figure>

## Examples of Basic Connectables:

**Cables**

These heavy-duty high-voltage cables are only used between station engines and related machinery.

Two “I” shapes can cross each other while maintaining separate circuits; they do not have a junction box like the similar “X” shape.

Though similar to wires, wires are more complex (see the “Wire Adjacency Connection” section for more details).

<figure><img src="https://lh4.googleusercontent.com/JC2IdTInQmp3RNZ5qGN7Mw--qZGAOYydJ6cc0eOvamhbGwwNaJTZZ78YwA3ZqVxpp6obxXdzOrS4kwtvpScqSJ6oBK_eJ_-1N5EOOOCFtPxSzeSb8QR1PTqtgOXoonAhY60n7UnW4-Jg83HkYNV6mA" alt=""><figcaption><p><strong>Cables</strong>. Connectables separated (with indicators) and combined.</p></figcaption></figure>

**Conveyor Belts**

Currently, these do not use a “T” or “X” shape so we can either add those or resolve how a straight piece may connect in such a situation as seen in the image (these may need to get their own unique adjacency connector in the future).

<figure><img src="https://lh3.googleusercontent.com/KO4exPM-f8PY5G0MNTltSfhe_jstY7cMgDaijQz-xyXoBBJk85ZzDGIDAzIDJwu5d4gBw4VbobboBaO6Gxv5n9zx-DGr_UsnItxvl6JKXAlmMV5tcLSYOLZp9mtVmaYyK9geDGU6wzWiBTs8ceoImg" alt=""><figcaption><p><strong>Conveyor Belts</strong>. Connectables separated (with indicators) and combined.</p></figcaption></figure>

**HE Pipes**

Heat Exchange Pipes don’t require an “O” shape.

They do however have an special “I” shaped called a “Junction” which connects between the HE pipes and regular pipes on the 4th layer (see the pipe adjacency connections section for more info).

<figure><img src="https://lh3.googleusercontent.com/Ed1P0S17791EkeRctTctEsxv_pKctqGkAO7Fen42tdt1VG9fZh1uSQHPfRKEvYRnIvf1jK8ayeOV95AunPAayaftVOZjlOhW1CHansexPNnViJvzUczuqAsTASIBkBPz_JHvVtyYyjm7XGJdkJ7nLQ" alt=""><figcaption><p><strong>HE Pipes.</strong> Connectables separated (with indicators) and combined.</p></figcaption></figure>

For more info, cinsult Advanced Adjacency Connections
