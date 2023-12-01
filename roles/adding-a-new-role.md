---
description: This page describes how to add a new role into the game
---

# Adding a new role

The first thing you need to do to create a new role is to go to **Assets/Content/Data/Roles**, either duplicate an existing role or right click and go **Create -> Roles -> RoleData**, name both the file and the "Role name" variable as the name of the role.

![](<../.gitbook/assets/image (36).png>)

Role Name: the name of the role\
PDA Prefab: the PDA prefab that will be spawned in the player's inventory\
ID Card Prefab: the ID Card prefab that will be spawned inside the PDA\
Permissions: the list of permissions the ID Card will have.\
Loadout: the loadout that will populate the player's inventory at round start.



To create a new loadout go to **Assets/Content/Data/Roles/Loadouts**, right click and go **Create -> Roles -> Loadout**, there choose the items that will spawn in the player's inventory.

![](<../.gitbook/assets/image (48).png>)

Check which slots will have items and then set which items will be spawned in the droplist that will show, remember that these items have to be registed in the AssetDatabase for them to appear in the droplist.

Now go to the **StartingRoles** asset in **Assets/Content/Data/Roles** and add the role to the list.

![](<../.gitbook/assets/image (41).png>)

Drag the Role data into the slot and set how many players can play that role per round, setting it to zero means there is no limit.



Remember that it is possible to create ID Cards with permissions inside the game, which would effectively allow more people to play the same role that what is initially allowed, a player's role is dictated solely by their ID Card, which can be stolen or dumped.
