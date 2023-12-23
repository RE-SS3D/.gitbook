# Directional Adjacency Connections

Directional connections use the “Directional Adjacency Connector” script. Directional connectables, unlike most connectables, have a distinct front side and back side (ex. modular seats). They can be manually rotated in the editor and game due to this directional nature. Their default rotations are set to ‘north’.\
These directional shapes are defined below:

<figure><img src="https://lh5.googleusercontent.com/NIzpFkj6Zxm3cAcmDqqurrfTPCGE8KKVaTjvAern7IfZ3D4ryjr1RmmVf6Pnx8P2ZWht4PNRj3LFs52F959cEq-QUTwa-PeM6BdmldZzo3iLNGI3DWi6yXxWeQG9ZN0Z6-6EJ4uDBnwwA3RJnIbPmQ" alt=""><figcaption><p>Modular couches</p></figcaption></figure>

O - A variant with no connections.

Lin - An “L” type variant which, according to its design, bends inward.

Lout - An “L” type variant which, according to its design, bends outward.

I - A variant shaped like an “I” but rotated 90°, with 2 connections, 1 to the east and 1 to the west.

Uright - A variant shaped like a “U” but rotated so the only connection is to the east.

Uleft - A variant shaped like a “U” but rotated so the only connection is to the west.

### Examples of Directional Connectables

#### **Chapel Pew**

<figure><img src="https://lh3.googleusercontent.com/eIsNmxFLOWfgda9G-oNTTJP-uNemY4AzSzKNlLcGbHtSfgtknrMRSqSqDahf17KAq5wja4NUFVG9qumV7YEQe3jmC62s8sOI7wDM9mZxUUB9XihET6TtSw3Bv3OvkEmpYXYCRmjiMdIrh9NkQXjFZg" alt=""><figcaption></figcaption></figure>

Chapel Pews are the basic version of directional connectables as they do not have any corner (“L” shaped) pieces, in theory they could be added though.

#### **Diner Booth**

<figure><img src="https://lh5.googleusercontent.com/xIB8rHsbT1gI_JdgUD5MT2YqKVtzCVCLFu8ubDxPbIQAoWpUXaTgi_bCo8EGHve998nsIoFMDUoRMESo73RW6rlwSXXAdfzVgiYtHXblSKCwWrmEGCyXg5Tpf9Pl58ZMn21VAlxDt7JwRdFvCM-zNg" alt=""><figcaption></figcaption></figure>

The Diner Booth is an example of a more typical use of a directional connectable for modular seating as they include corner (“L” shaped) pieces.

#### **Sofa**

<figure><img src="https://lh4.googleusercontent.com/wkRdT8bgmkdX_KZxe9L1aMLlO87-49XHOZwUmyAQrMPOUOxI-J0QuUB7sbfx9552sgN-sfEJOM7czlLg1A7avfUmJjH45XhdybWnreP7x85NVUtnzvUWn532ZxmKVO33ZwKiUgY-QnFZiHNv0L0jJw" alt=""><figcaption></figcaption></figure>

The Sofa is very similar to the Diner Booth, but it’s also a good example of adding style variants.

Style variants are simply a variant with an alternate art style. The Sofa’s example is the addition of armrests.

The armrests by their nature are only required on the end shapes of the sofa (“Uleft” and “Uright”) and on the singular sofa shape (“O”).

Other examples of directional connectables that are not fully realized yet may include things like railings and fences...

## How those directional connect to each other?

### Number of neighbors

Directionals can't connect to more than two neighbors. Once they are connected, putting any new directionals near them won't update them, unless a neighbor is disconnected.

<figure><img src="../../.gitbook/assets/image (31).png" alt="" width="295"><figcaption><p>The Lout shape booth is fully connected and doesn't care about the other neighbors.</p></figcaption></figure>

### Removing a neighbor

When removing a neighbor, a connection is free, and the directional will look for other adjacent directional to form an eventual second connection and change shape.

<figure><img src="../../.gitbook/assets/image (30).png" alt="" width="375"><figcaption><p>Booth before removing a neighbor and after.</p></figcaption></figure>

### Configuration priority

When a directional has to change shape and has multiple options (LIn, LOut, I), the directional will choose shape in the following order:

* I shape
* Lin shape
* Lout shape

This order is arbitrary, but it's necessary to define one as some cases are not well defined without it.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption><p>Before and after removing the south connection of the LOut shape, see that the I shape takes priority over the LIn shape.</p></figcaption></figure>
