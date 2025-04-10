# Disposal Adjacency Connections

Disposal connections use the “Disposal Adjacency Connector” script. Disposal connections are based on the basic connections and are similar to the other pipe connections. The disposal models themselves actually reside beneath the floor that the player walks on.

There is no need for the traditional “O” or “U” shapes but there are some unique “U” type shapes (see below). The “I” and “L” shapes act the same as they do in the basic connections.

The “T” shape acts the same in principle as well but is accompanied by arrow overlays. Due to the nature of disposals (objects travel through them), “T” shapes have a designated ‘exit’ connection side to determine which direction the object paths join into. This direction is represented by the arrow overlays (more info in the disposals documentation).

There isn’t a significant need for the “X” shape either but we do have one modeled and in theory the same directional arrows could be made for it to work the same as the “T” shape.

The unique disposal shapes are defined below:

<figure><img src="https://lh3.googleusercontent.com/-G4tZ9jhJbdnmMR2C9vy6uSlB723WcSK7iX1g7gpls22wcGjJIF6iJNRp3OBP3LNRoBLCEs4Irsv3-N_MIgICrdORDMoO6WP4uu2emNLL6fuWFmxFzBGonUgUm0k2FkLNL-pKXEC1Tt2BiDMZH6stA" alt=""><figcaption></figcaption></figure>

Broken - A special “U” type variant which replaces a variant when it gets abruptly destroyed (more about this below).

When a disposal pipe variant gets destroyed, instead of alerting nearby connections that there is no longer a connection at this location and to update their own shape as a result; we maintain connections to this tile and replace it with 1 broken variant per undestroyed connection.

<figure><img src="https://lh4.googleusercontent.com/nZM3jprlrNm_5bNZO8XvHXisHCn9KYnAhdYP5dS2BMzfIXNX1dAZb2Pk8rtc8tbYp6gaE6Xs8ZjuGgWn6bqdK2KfXvNg0vl5v8e3ZcwV1tcb85SnuYlIakZGQtJZ01GAnKL3bpmcOg-XqCkDGgTL9Q" alt=""><figcaption><p>This should naturally result with broken ends regardless of the size or shape of the destructive force.</p></figcaption></figure>

Vertical - A special “U” type variant which connects to the north as well as turning upward and connects vertically to above-ground disposal machines. Pipes & wires cannot exist on a tile with a vertical disposal due to major clipping.

Vertical pipes only connect to pipes in one direction, by default this direction is toward the front of the machine that is connected above. However they should be rotatable (without rotating the machine above.

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>
