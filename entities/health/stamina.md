---
description: The strength to go on.
---

# Stamina

Stamina system is responsible for managing the player’s ability to run around. It is a single value which initially depends on character’s species and can be modified in the round by doing exercise (or reduced by getting fat, contracting an illness or getting injured). The amount of stamina available is reduced with running, fighting, carrying heavy objects or doing any other physical activity that can make people tired IRL, but is recovered over time to the maximum stamina amount.

Improving stamina is done by doing said physical activity, the max amount of stamina is increasing with every N spent stamina.

Stamina can be recovered quickly in a variety of ways as shown below, ordered from slow to fast recovery.

* Walking (instead of running)
* Staying still
* Sitting
* Lying

There’s a variety of ways the Max amount of stamina or it’s regeneration speed can be reduced. For example, the Max amount of stamina is reduced by (100-x)/2 where x = health of both lungs, and regeneration of the stamina is reduced by total OXY damage. (all numbers are placeholders, here and below)

For a healthy character stamina should regenerate fast enough to not matter much, and for combating, injured or tired character it can serve as a more flexible cooldown system. At least, that's the idea of how it should be balanced.
