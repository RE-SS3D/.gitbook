# 🏗 Construction

Crew members should have the ability to alter, fix and or dismantle the structure of the [station](../tilemaps/stations.md), that's where the Construction system comes in.

Which means that any person should be able to create or interact with walls and floor ~~and ceiling~~ of the station, should they have right materials and tools. The mane philosophy is allowing the player to affect the structure with a simple click of a mouse.

_Rules of_ [_connectables_](../connectables/) _apply._

### Tilemap Layers

Stations are like onions. They have layers.

The bottom layer is Plenum; the base structural layer. All the other layers are built upon this one. The plenum layer can have a few different models here like lattice and catwalk, but the main one is the plenum. This main model much like the layer it shares a name with is the core of the station's structure. Many things can be built on top and within the plenum.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p>A set of uncovered plenums with several pipes laid into them and wire just on top.</p></figcaption></figure>

The plenum has room for 3 layers of atmos pipes and 1 layer for the large disposal pipe.

Immediately on top of the plenum layer is the wires layer (this may get lowered slightly down into the plenum)((we may triple this up at some point like /tg/). There's 2 main types of wires at the moment. Wires and Cables. Cables are basically the heavy duty wires.

Above cables there is 1 layer for floor tile, 1 for atmos pipes, a couple for furniture, a few for floor overlays, and 1 for walls. On wall, there are 3 layers of wallmounts (times 4, 1 for each cardinal direction).   \[\[\[add more recent image below]]]

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>A set of pipes and junctions connecting pipes below &#x26; above the floor (we will only have 1 layer above the floor, not 4).</p></figcaption></figure>

Floors are a layer made to support furniture, walls, and even the captain's fat ass.

Walls are pretty self-explanatory: it limits the room, seals and insulates the rooms from the sides ~~and supports ceiling:~~

### Z Layers

NOT IN THE CURRENT ROADMAP but it's fun to conceptualize the idea of possible z-layers for the station itself.

{% embed url="https://ss3d.space/assets/img/posts/19.10.01/EikoZSwap.mp4" %}
A man can dream, right?
{% endembed %}
