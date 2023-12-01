---
cover: ../.gitbook/assets/ProbablyNot_Chase.png
coverY: 0
---

# 👜 Inventories

Inventories represent in part what player can hold on themselves, including clothes, what they have in hand, in their pocket, in their bag, but also what they can access through a container. When a player open a toolbox and use an interaction to view it, the toolbox's container become a part of the player inventory as long as the player is observing the content of the toolbox.

Inventories in SS3D rely on the container system. Every container on a player and every container viewed by the player is part of its inventory.&#x20;

## Functionalities

The inventory is currently responsible for the following functionalities :&#x20;

* Transferring an item to a container, eventually in a given slot.
* Spawning an item from a container back in the world.
* &#x20;Firing the open animation when a container is added first to an inventory.
* Switching between activated hands.
* Adding and removing container to itself, firing event when doing so.
* Checking server side some of the above can be done by a client asking to perform those actions. That would for instance include checking if a player can interact with their hand with a given container.

## Dependencies

Containers UI are depending a lot on the inventory system, when adding a container to an inventory, it's UI(if it has one) will be displayed.

The Roles System depends on it as well, as it needs to spawn role items in the inventory at the beginning of the round.
