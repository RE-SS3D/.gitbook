---
description: How does the character do stuff
---

# 🖐 Interactions

This is the page for interactions design in terms of how a non-programmer can understand. Interaction in that sense is a way for player to use the objects around them.

The station is filled with objects that are complicated and have several functions, and yet we aim for a fluid and streamlined gameplay process. In other words, doing stuff should not be hard for players and they still should be able to do everything developed for an object.

Overall, interactions should be simple: click on thing - use the thing IF character has an empty hand. If it's hand is not empty, character should try to use the item in hand on the clicked object in a way that makes sense.

## Empty Hand

So. How do we do it?

In essense, all objects should have a <mark style="color:red;">Primary</mark> interaction. Something that should be done with that object by default: light switch should be clicked to be switched, a tool should be picked up on click, a fridge should be opened or closed on click.

And not ony that can be different things for each object, some objects might (and will) have multiple functions. That raises the question "how do we deal with things that have several possible actions"? For example, a blender can be opened/closed, turned on/off and picked up/placed down.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>Interaction wheel for a radio (debug)</p></figcaption></figure>

For that we have an interaction wheel. The access to it should also be pretty simple. One way of doing that is holding a LMB on an object for a fraction of a second to have the interaction wheel display it's options, move the mouse in the direction of the desired option and release the LMB to select it.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption><p>Blue LMB is hold, Red LMB is release</p></figcaption></figure>

Alternatively, use RMB which comes down to a personal preference, so it might be worth to have both options to choose from.

Interaction wheel is able to contain up to 8 interactions options at the moment. Most objects have less, and those that have more would probably have it's own UI, like the door wires or a computer console (see [here ](http://127.0.0.1:5000/s/o88TIFUbxlEVDM0ZH62q/2d/ui-elements/windows)for art info).

Still, some things have few interactions in them, their main one and a secondary one or two. For example, most people wouldn't want to open a wheel every time they'd like to pick up something. So, that also needs a faster way of doing.

So far, a LOT of stuff can be just picked up, a LOT of stuff can be opened (as a container) and a LOT of stuff have some sort of main singular function. So, it boils down to 3 most common interaction types:

1. Make it do what it's made for if you can. Access it's UI, turn it on, open it's valve, make it do a thing
2. Change it's location if you can. Either grab it and hold it in hand or grab it and try pushing/pulling it away
3. Open it up if you can. If it's a container, you should be able to attempt to open it

Have overrides for each of those three that work on all objects that it can.

* Button for MAKE IT DO STUFF + LMB would make it automatically do stuff even if it's intended to be picked up. Example: honk the horn on the table without picking it up, blend something without opening the blender first
* Button to RELOCATE IT + LMB would make it automatically pick it up OR (if it's too large or heavy) to puch/pull it. Example: Drag a janitor trolley away without opening it first
* Button to OPEN IT + LMB would make it automatically reveal it's inventory, if it has one. Example: open toolbox without the need to pick it up first.

A simple LMB click on something still would do the interaction that is considered <mark style="color:red;">Primary</mark>, while the rest would still be available in the interaction wheel, but if someone wants to access those interactions immediately, they can do it right away.

So, for example:

* Shift + click = activate
* Ctrl + click = grab/pull/whatever
* Alt + click = access inventory

Now, access inventory has it's own page (or would be, once I'll get to it, add link later), but what does grab/pull means? Basically, some of the objects are small and light enough to be picked up, while others are not. So how do we distinguish, should the character pick up the thing or just drag it? One way to do it is to make those mutually exclusive. You don't drag the spoon or a can or a gun, you pick it up and bring it where it's needed. And you don't pick up the locker or a piano or a safe, you drag it.

A chair, a large box a person can reasonably pick up, a sack of potatoes, those are the Medium category, as those can be both dragged and picked up. This would include small furniture objects like chairs, stools, microwave, blender; large items like boxes, sacks or packages; small entities like dogs or slimes. So how do we decide when to pick up and when to drag? We check the number of available hands, as it's hard to pick one of those things with one hand and there's no reason to drag them with both free hands.

* large objects - always drag
* medium objects + one free hand - drag
* medium objects + two free hands - pick up
* small objects - always pick up

## Something in hand

Speaking of picking things up. If the character is holding something in a hand, then if player clicks on any object, the character should try applying the item in hand to the object in a way that would make sense.

Some things are obvious. A pistol mag inserts into an emptied pistol. A disk fits into a console. Welder should weld/un-weld the locker if applied to it. The whole system of crafting relies on this kind of interaction: applying an item to another item to make a new item (see crafting page (add link)).

And then some things have a <mark style="color:red;">Primary</mark> interaction they do regardless of where the player clicked. Horns always honk, boomboxes always blast music, lighters always burn, guns always shoot.

However some of the items have a Secondary interaction in them as well. Guns need to be unloaded, boomboxes do need to change songs, etc. And those actions are guaranteed to be needed urgently. Not to mention ways to drop something in a hand or quickly access it's inventory. Seems pretty similar to what we've discussed in the previous part about interaction wheel and overrides, so let's use those here too:

* hotkey #1 = use primary function
* hotkey #2 = use secondary function
* hotkey #3 = drop the thing immediately
* hotkey #4 = access it's inventory

Those interactions are still going to be in a wheel, if the item supports it, but it's an extra option is still going to be here for the players.

Now, in question of how to place the item in the world with precision and not just drop it, there are several suggestions. One of the most convenient is drag-and-drop from hand slot to the particular place in the world. It does not require an extra hotkey and is fast enough. Still, for those players that place a lot of things manually, it might be worth having a key to hold when clicking on a place to put an item, though the scenario where it's absolutely needed remains inlikely, as people rarely have more then two hands.

When the animation system is done, the drag-and-drop option would also allow for such things as "Procedural animation that plays where player starts placing object and blends their hand position to where the mouse is going until it eventually lets go, placing the object."
