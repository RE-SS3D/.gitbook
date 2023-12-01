# Developer Guide

## Developer Guide

### Adding a permanent container to inventory

1. First you'll need to set up a public reference to an AttachedContainer  in Inventory.cs. (give it a name representing the container, such as "LeftPocket"
2. Then, add an attachedContainer script on the prefab with the inventory script(such as Human) wherever you want it to be. To set up the container, you can draw inspiration from containers already set up on the Human prefab such as the left hand container on hold.l game object.
3. Set up a reference in inventory editor to your newly created AttachedContainer.
4. It's all good !&#x20;

Now if you want to interact with this container through a similar UI as the one for hands or pockets, you'll have to check up our UI guide coming soon.
