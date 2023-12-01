---
description: Seize what you need.
---

# Grab

## GRAB

CTRL+LEFT\_CLICK on an active target character, while having an empty hand and Combat mode is <mark style="color:green;">disabled</mark>, will result in grabbing the target.

<figure><img src="https://lh6.googleusercontent.com/_HkDUDU9H6QhNPwwWpghqY1SXY0OUMWPZxuHHecQza3eIBAb-2j7QFzifBynqchYFMGY2gQk3aS5evN4XW_uXDkzNNX2xN3a_VMAHY6KyMUfGNk-pjI6ujOxE-W-F9piVVZrKFt0M6WckPE41wz6-Q" alt=""><figcaption><p>Clicking on another character while not intending to engage in combat (see green UI element) results in softly grabing the target.</p></figcaption></figure>

If used on humanoids, the grab on the torso allows the player character to pull or push the target with it.

Grabbing the hand of an active target character while Combat mode is <mark style="color:green;">disabled</mark> will result in an attempt to extend own hand to the target character.

* If the player character’s arm is not empty, target character has an option to take the item, as long as they have an empty hand.
* If the player character’s arm is empty, target character has an option to put their own item into the extended hand, as long as they have an item in hand OR to shake hands, if both characters have an empty hand.

Grabbing the hand of an active target character while Combat mode is <mark style="color:red;">enabled</mark> will result in an attempt to DISARM: take an item from their hand or make target drop it from the said arm (if it’s not empty), or prevent the target from using their arms to fight and/or grab (if it’s empty).

Grabbing the leg substantially slows the target’s movement. (if too complicated to implement or confusing in gameplay, might be worth automatically switching to the arms or body)

Grabbing the inactive target by any bodypart should result in an animation of the player character dragging the ragdoll (or IK-rigged) target by the selected bodypart. (Also works for inanimate objects)
