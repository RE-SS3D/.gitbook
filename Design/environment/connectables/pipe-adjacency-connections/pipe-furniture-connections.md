# Pipe Furniture Connections

Pipe furniture is basically any machine that connects to (standard) pipes.

Pipe furniture connects to pipes by overlaying half pipes ('U' shapes) on the same tile and layer as the furniture to connect to a pipe on an adjacent tile and same layer. The reason we use multiple 'U' shapes overlaying a furniture instead of a multi-directional shape, like 'T' for example, to connect in multiple directions is because the pipes on either side of a pipe furniture are part of individual pipe volumes separated by the furniture. They may also be colored individually.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### Pipe Furniture Types

#### On-Pipe

Pipe furniture that is small and sits on the pipe layers. On-Pipe pipe furniture can exist on ANY of the 4 pipe layers (only 1 at a time). Examples - pumps, valves, meters, etc.

On-Pipe pipe furniture only connects in 2 directions (opposite of each other, creating what looks like a straight 'I' pipe shape).

On-Pipe pipe furniture are small and exist on a single layer therefore multiple can exist on a single tile, 1 for each layer (with clipping).

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

#### On-Floor

Pipe furniture that sits on the floor level. On-Floor pipe furniture can be directly connected to via pipes on the floor layer (pipe layer 4). Examples - filters, mixers, injectors, connector ports, freezers, heaters, etc.

Some can connect to pipes in any direction, some only in 1, and other may be in-between.

On-Floor pipe furniture are large but since they exist on the floor layer and there is only 1 pipe layer above the floors, they do not obstruct the other pipe layers below.

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

#### Under-Floor

Pipe furniture that sits below the floor level (in the plenum level). Under-Floor pipe furniture can be directly connected to via pipes on any of the below floor layers (pipe layers 1-3). Examples - layer manifolds, etc.

Some can connect to pipes in any direction, some only in 1, and other may be in-between.

Under-Floor pipe furniture are large and may block/interact with all pipes below the floor (layers 1-3).

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

#### Both-Floor

Pipe furniture that sits below the floor level but also extends up above the floor level. Examples - special layer manifolds, etc.

Some can connect to pipes in any direction, some only in 1, and other may be in-between.

Both-Floor pipe furniture are large and block ALL pipes both under the floor AND the above floor layer. They also block wires AND floor tiles.

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>
