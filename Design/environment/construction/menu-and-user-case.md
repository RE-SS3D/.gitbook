# Menu and User Case

There is a variety of things one can make with a torch and rods of metal. From floor girders to wall girders to a base for a vending machine. So, when the materials and tools allow for several options of constructions, the player must be presented with choice. This is proposed to be done via construction menu:

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>An example for how a construction options menu should look</p></figcaption></figure>

This menu should include the name of the available structure, it's picture, description, materials and tools for it's creation and it's careful dismantling, if possible.

Once chosen, the structure's model with applied holographic shader should be displayed, attached to the closest adjacent tile to where player is standing and facing. Green shader for when the tile is free and red if it's not. Player character should be able to move while choosing the construction tile and the shadered model location should be updated according to the rules above. Player should also be able to rotate the structure if necessary, and also to quickly disable construction mode in case of an emergency. And, obviously, when location is available, player should be able to confirm the chosen location.

Once the location is chosen, the character should play a crafting animation, resources should be expanded and a bunch of smoke and particles should be played to obscure the change from empty space to the freshly built structure.
