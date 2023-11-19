# Pipe Adjacency Connections

Pipe connections use the “Pipe Adjacency Connector” script. Pipe connections are based on the basic connections and are also similar to the disposal connections.

<figure><img src="https://lh6.googleusercontent.com/l34krKKQjHYIDsjkS_aiiOFLNSZmC4z71oaMsrUnMx5YjhGDthYm3cQPC_vnv8RnF_ECESPq6ZnBNj5jZN47etaP1UqfV8SL9jBGomosSTdFzIQ3egWRA6J1T6UX8Am3rtqDMjNVocPnHBTlEy0LHw" alt=""><figcaption></figcaption></figure>

Pipes have 4 layers, the first 3 layers reside in the plenum below the floor with the disposals, while the final layer rests just above the floor.

You’ll quickly notice that pipe layers 2 & 4 are centered, while layers 1 & 3 are offset. Due to the offset nature of layers 1 & 3 they require additional model shapes and use a more complex connector script (see the “Offset Pipe Adjacency Connections” section below).

Pipe Layers 2 & 4 work just like basic connections (“U”, “I”, “L”, “T”, and “X”) with one exception. This exception is defined below:

<figure><img src="https://lh4.googleusercontent.com/pbpG_uMMnW6YhAN_LSTbuYxYx_NoMIapJBqo9YkMQnxNzFnw2gQc0eUpqqjv6Yv8xgt6Af3mpuht8k5ofhsT7Rl3y64JHhR2KqsqHixLgvPzJtroCb--qKtxv1sKhTznK4bZ07wcW0rsnKoue8BP9w" alt=""><figcaption></figcaption></figure>

Broken - A special “U” type variant which replaces a variant when it gets abruptly destroyed.

Similar to disposals, 2 “I” shaped pipes can cross each other perpendicularly. Although they are clipping through each other, they are not joined like an “X” shape.

Unlike disposals, pipes have another overlapping property. 2 “L” shaped pipes can coexist on the same tile as long as they are oriented opposite of each other. (In SS13 the pipes clip in this situation but we designed our models to prevent clipping here.)

## Offset Pipe Adjacency Connections <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

Offset pipe connections use the “Offset Pipe Adjacency Connector” script. Offset pipe connections are based on the regular pipe connections and exist on pipe layers 1 & 3.

The primary difference between the pipe and offset pipe connections is what the name implies, the offset pipes are offset. Due to them being offset, they cannot simply be rotated for different orientations. To solve this, we use additional models for the different orientations. These offset shapes are defined below:

<figure><img src="https://lh6.googleusercontent.com/HLpYplNOKbQiZTQ9hMwHhAvcIkh8TTfF6MFu4Ve4sEkBF2Li4vBBXnSBtMJAYrhCQZG-BRhyb5b-lo3Wpr6I4-MmoEVOsfoQboIPZInk5sQAfk0fmZSU2McE1xLD6xenjTmL_Trtwn2_LoipnomK9g" alt=""><figcaption></figcaption></figure>

U1 - A “U” type variant which connects to the north OR west (rotate 90°).

U2 - A “U” type variant which connects to the south OR east (rotate 90°).

Broken1 - A special “U” type variant which connects to the north OR west (rotate 90°).

Broken2 - A special “U” type variant which connects to the south OR east (rotate 90°).

I - A regular “I” type variant which connects to the north and south OR east and west (rotate 90°).

L1 - A “L” type variant which connects to the north and east (not meant to be rotated).

L2 - A “L” type variant which connects to the north and west (not meant to be rotated).

L3 - A “L” type variant which connects to the south and east (not meant to be rotated).

L4 - A “L” type variant which connects to the south and west (not meant to be rotated).

T1 - A “T” type variant which connects to the south, east, and west (not meant to be rotated).

T2 - A “T” type variant which connects to the north, east, and west (not meant to be rotated).

T3 - A “T” type variant which connects to the north, west, and south (not meant to be rotated).

T4 - A “T” type variant which connects to the north, east, and south (not meant to be rotated).

X - A regular “X” type variant which connects to all 4 cardinal directions (not meant to be rotated).

<figure><img src="https://lh3.googleusercontent.com/pbUx0MadXhNslql_9AG9ixByupO0iBZ40ljRp5YCTWW-2ehNmuSYIDp7kmV2e9pHqhUgcNmA6uTVssUYTP4zfTiF67MNn7zgYLRdmTsJFIFYhlwCosPD8l-ydR8H3FpQ8tpRDYQopChXHN5n1180Qw" alt=""><figcaption></figcaption></figure>

What's also to be considered:

* Pipe Machinery Adjacency Connections
* Transit Tube Adjacency Connections
