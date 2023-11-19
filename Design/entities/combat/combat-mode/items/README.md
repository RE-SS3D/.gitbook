# Items

#### ITEMS

There are several options proposed on how to deal with item interactions when tied to the intents, but one overall rule remains: items that are made to be used on a character should be easily used on them if needed. In other words:

LEFT\_CLICK on an active target character, while having an item that's marked as "helpful"  in hand, will result in the primary interaction of the item applied on the target character. (Works <mark style="color:blue;">regardless</mark> of the player's current mode.)

(For example, clicking on another character with a syringe or food in your hand will make you attempt to inject or force feed them)

LEFT\_CLICK on an active target character, while having an item that's marked as "harmful", either "melee" or "ranged", in hand, will result in an attempt to use the item on the target character accordingly (see section WEAPONS). (Works <mark style="color:blue;">regardless</mark> of the player's current mode, but this action automatically <mark style="color:red;">enables</mark> Combat mode)

The rest is divisive. The items that were not made to be used on humans, ideally, should still be used on them in some way. For example, the toolbox.

Option true to the SS13: LEFT\_CLICK on an active target character, while having an item that's not marked as "helpful" or "harmful" in hand will result in an attempt to bash the target character with this item. (Works <mark style="color:blue;">regardless</mark> of the player's current mode.)

This, however, has a problem of player/character disconnect (RP stuff) and it generally wouldn’t make sense hurting someone with the HELP intent. For this purpose, another set of options was suggested:

LEFT\_CLICK on an active target character, while having an item that's not marked as "helpful" or "harmful" in hand, will result in:

* a message "You can't help this person with your hands full" (Works <mark style="color:blue;">regardless</mark> of the player's current mode.)
* an attempt to bash the target character with this item. In <mark style="color:red;">HARM</mark> mode, the rules for improvised melee weapons apply. In <mark style="color:green;">HELP</mark> mode, the damage is reduced to ⅓ or less, depending on the traits of the item, such as "sharp" or "chemical" or "breakable"
* an attempt to bash the target character with this item. In <mark style="color:red;">HARM</mark> mode, the rules for improvised melee weapons apply. In <mark style="color:green;">HELP</mark> mode, the damage is reduced 0, so only the effect of the hit (such as the animation and the sound) remains
* an attempt to bash the target character with this item (In <mark style="color:red;">HARM</mark> mode) or an attempt to drop the item and help the target character with a freed hand (In <mark style="color:green;">HELP</mark> mode)
* an attempt to bash the target character with this item (In <mark style="color:red;">HARM</mark> mode) or an attempt to offer the said item to the target character (In <mark style="color:green;">HELP</mark> mode)
