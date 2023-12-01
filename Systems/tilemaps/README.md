---
description: Functions and features of the tilemap system.
cover: ../.gitbook/assets/ProbablyNot_Chase.png
coverY: 0
---

# 🗺 Tilemaps

_**For mapping design see the Maps Design document linked below.**_

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

The tilemap system forms the basis of the space station and is responsible for the creation and management of all items and 2-dimensional tiles that compose the station. Every static object such as floors, walls and bolted objects (i.e., fixtures) are part of the tilemap. Other systems such as construction or atmospherics have a close integration with the tilemap.

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

## Features

**Grid-based design with chunks**\
The new design leverages collections more, which allows us to go faster through objects that are on the same layer. Next to that, the map is divided into chunks of 16 x 16 tiles. This should allow more flexibility in the future in cases where we only need to look at objects nearby, without the need to go through the entire map.

**Saving and loading**\
The tilemap is now fully serialized and can be saved and loaded at will. This allows a few options like the ability to save chaotic stations at the end of a round for other game modes, but will also make resolving merge conflicts in the map easier.

**Multi-tile objects**\
Objects that are bigger than a single tile can now be successfully added to the map. You can now place a cryo tube again without having to worry about it colliding with other nearby objects.

**Items**\
Items are now part of the tilemap and can be placed and removed. This means that they are also part of the save system.
