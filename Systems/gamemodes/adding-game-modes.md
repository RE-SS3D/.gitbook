---
description: This page describes how to add a new game mode with it's set of objectives
---

# Adding game modes

Creating a new game mode is generally simpler than adding an objective, you just have to create a new class inheriting the **Gamemode** class with a **CreateAssetMenu** property and... that's it! you don't even have to add any code to it unless you want to change something about the internal working of gamemodes, which is beyond the scope of this guide.&#x20;

Let's recreate the Nuke gamemode as an example, first go to **Assets > Scripts > SS3D > Systems > Gamemodes > Modes** and create the new class there, we'll call it **NukeGamemode.**

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>The class just inherits the Gamemode class and sets up a CreateAssetMenu property for a ScriptableObject, it doesn't need to implement anything to work.</p></figcaption></figure>

Now we just have to create the **ScriptableObjects** for the game mode, for that we go to **Assets > Content > Data > Gamemode**, we'll need multiple scriptable objects for each game mode so it might be a good idea to make a new folder for each game mode, so we'll create a **Nuke** folder for ours.

First we need to create a **GamemodeObjectiveCollectionEntry,** which is used to control how the objectives will be distributed to players, to create one we right-click and go **Create > Gamemode > GamemodeObjectiveCollectionEntry**, we then have to set it's properties, we do it as follows:

* Gamemode Objective: the actual objective's ScriptableObject.
* Assignment Probability: the probability of the objective being assigned to a player.
* Remaining Assignments: how many objectives of this type can be assigned.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

After that we need to create a **GammodeObjectiveCollection** which is a collection of objective entries that a game mode can assign to players, to create one we right-click and go **Create > Gamemode > GamemodeObjectiveCollection,** we then just have to put all of the objective entries into the collection's list.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

We now have everything set up to create our actual gamemode's ScriptableObject, for that we right-click and go **Create > Gamemode > Modes > NukeGamemode** (the name of your gamemode), we then just have to set up it's name and it's GamemodeObjectiveCollection.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Done, the game mode is completed, to test it we just have to go to the GamemodeSystem game object in the Lobby screen and set the round's game mode to ours.

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>
