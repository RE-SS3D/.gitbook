---
description: This page describes how to add new permissions into the game
---

# Adding a new permission

To add a new permission into the game go to **Assets/Content/Data/Traits/Identification/Permissions**, right click and go **Create -> Inventory -> Traits -> Permission**, just name it accordingly.

To add the permission into a role, just add it to the Role Data's permission list

![](<../.gitbook/assets/image (33).png>)

This permission can be checked inside of a script throught the Inventory class, by using the **HasPermission** function.

\
\
For example, the Security Locker currently checks for a **Security** permission to be both locked and unlocked. the **Unlock Locker** interaction checks for the permission by getting the player's inventory:

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption><p>Here we get the player's inventory through the hands that executed the interaction, with it we have access to the HasPermission function, we then check if it has the "permissionToUnlock" permission.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption><p>The permissionToUnlock field is set via the inspector.</p></figcaption></figure>
