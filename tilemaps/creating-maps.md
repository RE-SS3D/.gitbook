---
description: Using the tilemap creator.
---

# Creating Maps

### Getting Started

To get started with the creator, run the game and press **B** after spawning. This will bring the creator menu up.

![](<../.gitbook/assets/image (38).png>)



### Controls

* Press **left mouse button** to place an object
* Press **R** to rotate an object&#x20;
* Hold **left shift** to replace an existing object on the same layer
* **Click drag** to place/delete/replace in a line form
* **Alt+Click drag** to place/delete/replace in a square form

### Building indicators

<div align="left">

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption><p>Valid build location</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>Invalid build location</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption><p>Object will be deleted</p></figcaption></figure>

</div>

### Building layers

Each tile can hold multiple objects on different layers. The following layers are implemented:

* Plenums - These form the foundations of the station. Always required to be present before another layer can be build
* Turfs - Walls and floors go on this layer
* Wires - High, medium and low voltage wires
* Disposal - Disposal pipes fit in this layer
* Pipes - Atmospheric pipes go here
* WallMountHigh - Wall mounts that are placed high on the wall
* WallMountLow - Wall mounts that are placed low on the wall
* FurnitureBase - Regular objects such as chairs, tables and counters go here
* FurnitureTop - Objects that go on top of FurnitureBase. For example desk lamps
* Overlays - Indicators that fit on top of floors go here
