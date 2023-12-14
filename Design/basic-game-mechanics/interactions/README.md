---
description: How does the character do stuff
---

# 🖐 Interactions

This is the page for interactions design in terms of how a non-programmer can understand. Interaction in that sense is a way for player to use the objects around them.

The station is filled with objects that are complicated and have several functions, and yet we aim for a fluid and streamlined gameplay process. In other words, doing stuff should not be hard for players and they still should be able to do everything developed for an object.

Overall, interactions should be simple: click on thing - use the thing IF character has an empty hand.

## Empty Hand

So. How do we do it?

In essence, all objects should have a <mark style="color:red;">Primary</mark> interaction. Something that should be done with that object by default: light switch should be clicked to be switched, a tool should be picked up on click, a fridge should be opened or closed on click.

And not only that can be different things for each object, some objects might (and will) have multiple functions. That raises the question "how do we deal with things that have several possible actions"? For example, a blender can be opened/closed, turned on/off and picked up/placed down.

For that we have an interaction wheel.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Interaction wheel for a radio (debug)</p></figcaption></figure>

Interaction wheel is able to contain up to 8 interactions options at the moment. Most objects have less, and those that have more would probably have it's own UI, like the door wires or a computer console (see [here ](https://app.gitbook.com/s/o88TIFUbxlEVDM0ZH62q/2d/ui-elements/windows)for window UI info).

Still, some things have few interactions in them, their main one and a secondary one or two. For example, most people wouldn't want to open a wheel every time they'd like to pick up something. So, that also needs a faster way of doing.

So far, a LOT of stuff can be just picked up, a LOT of stuff can be opened (as a container) and a LOT of stuff have some sort of main singular function. So, it boils down to 3 most common interaction types:

1. [Move](move.md) - Change it's location if you can. Pick it up if and item or grab it to pull/push if furniture/entity.
2. [Activate](activate.md) - Make it do what it's made to. Access it's UI, turn it on, open it's valve, make it do a thing.
3. [Access](access.md) - If it's a container, you should be able to attempt to open/close it and see the inventory.

We will use modifier keys for these to override the primary interaction (examples below but otherwise see the [Controls page](../controls.md)).

1. CTRL + LMB  =  Move
2. Shift + LMB  =  Activate
3. ALT + LMB  =  Access

A simple LMB click on something still would do the interaction that is considered <mark style="color:red;">Primary</mark>, while the rest would still be available in the interaction wheel, but if someone wants to access those interactions immediately, they can do it right away.

## Object In Hand

If the character is holding something in a hand, then if player clicks on any object, the character should try applying the item in hand to the object in a way that would make sense.

Some things are obvious. A pistol mag inserts into an emptied pistol (move). A disk fits into a console (move). Welder should weld/un-weld the locker if applied to it (special). The whole system of crafting relies on this kind of interaction: applying an item to another item to make a new item (see [crafting page](../../actions/crafting/)).

And then some things have a <mark style="color:red;">Primary</mark> interaction they do regardless of where the player clicked. Horns always honk (activate), jukeboxes always blast music (activate), lighters always burn (activate), guns always shoot (activate).

However some of the items have a Secondary interaction in them as well. Guns need to be unloaded, jukeboxes need to change songs, etc. And those actions are guaranteed to be needed urgently.

Dropping an item will also have a hotkey (likely Q).

### Placing Object

Now, in question of how to place the item in the world with precision and not just drop it, there are several suggestions:

1. Drag-and-drop from hand slot to the particular place in the world. It does not require an extra hotkey and is fast enough.
2. Hold+Click for those players that place a lot of things manually.

When the animation system is done, both options should allow for such things as "Procedural animation that plays where player starts placing object and blends their hand position to where the mouse is going until it eventually lets go, placing the object."
