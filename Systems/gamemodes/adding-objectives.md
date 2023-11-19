---
description: >-
  This page describes how to add a new objective that can then be added to a
  game mode.
---

# Adding objectives

To add a new gameobject you have to first create a new script in **Assets > Scripts > SS3D > Systems > Gamemodes > Objectives.**

You may copy another objective that is already done to make your life easier, but the rules an objective has to follow are:

* It has to be a child of the **GamemodeObjective** class.
* It has to call the **Succeed** method to be completeable.
* It has to have a **CreateAssetMenu** property above the class.
* It has to be in the **SS3D.Systems.Gamemodes.Objectives** namespace**.**

Let's say you wanted to create an objective to picking up a BikeHorn

First you would create a new script that inherits **GamemodeObjective**, let's call it **PickupBikehornObjective**.

You would then have to set up the **CreateAssetMenu** property since the **GamemodeObjective** class is an **ScriptableObject.** you should also put it under the **SS3D.Systems.Gamemodes.Objectives** namespace.

You would then end up with this:

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p>I named the asset "GetBikeHorn" but it could be anything else, it is also better if you put it under Gamemode/Objectives/ so it shows together with all the other objectives.</p></figcaption></figure>

We now add the **pickedUpItemId** and **pickedUpPlayerCkey** private properties so we can hook them to the **ItemPickedUpEvent** and check if the picked up item was a bikehorn.

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

We now have to add an event listener to the **ItemPickedUpEvent**, we do that in the **AddEventListeners** method, we will then hook it to a **HandleItemPickedUpEvent** method.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>Here we hook the HandleItemPickedUpEvent to the ItemPickedUpEvent so the method in our class is called whenever that event is invoked.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>This method first gets the item and player data from the ItemPickedUpEvent, then it checks if the picked up item is a BikeHorn and if the player that picked up the item is the player currently assigned to this objective, if so it sets the pickedUpItemId and pickedUpPlayerCkey variables and calls the FinalizeObjective method.</p></figcaption></figure>

We usually call the FinalizeObjective to conclude an objective, but you could call either Succeed or Fail from any method, but following our practices we will do the check inside FinalizeObjective anyway.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>Just to be sure we check if the pickedUpItemId is not BikeHorn or if the player isn't the one assigned to the objective, if either isn't we just return and don't do anything, but, if there are no problems then we call Succeed and finish the objective.</p></figcaption></figure>

Now you just have to create the ScriptableObject, for that we go to the **Assets > Content > Data > Gamemode > Objectives** folder, right-click and go **Create > Gamemode > Objectives > GetBikeHorn.**

Now you just have to set up the properties for the objective as follows:

* Title: What is the title of the objective that will appear in the UI.
* Collaboration Type: if the objective is assigned to a single individual, multiple or if it's a competitve objective, meaning a single players can complete it.
* Alignment Requirement: If Traitors, Crew members, or both can get this objective.
* Min Assignees: Minimun number of players that will be assigned this objective.
* Max Assignees: Maximum number of players that can be assigned this objective.

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

Done, now you have succesfully added a new objective to the game!
