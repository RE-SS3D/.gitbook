# Basic Adjacency Connections

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

### Examples of Basic Connections

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
