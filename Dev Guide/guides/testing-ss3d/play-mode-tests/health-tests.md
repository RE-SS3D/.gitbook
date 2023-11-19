---
description: >-
  This describe a bunch of tests to perform when messing with things related to
  health.
---

# Health tests

### Killing a player by hitting on torso

**SETUP** : Just have a healthy human spawn, with the AttackBodyPartByClickingIt attached. Check that the damage amount is above 0 (should be 10 to quick test it). &#x20;

**TEST :** Press F a bunch of time while aiming with the mouse on the player torso until the player explode.

**RESULT** : You should see body parts flying, the camera should focus on the detached head, all body parts should disappear after a while and the head should too. After that, you're a ghost that you can control.



### Killing a player by hitting on head

**SETUP** : Just have a healthy human spawn, with the AttackBodyPartByClickingIt attached. Check that the damage amount is above 0 (should be 10 to quick test it). &#x20;

**TEST :** Press F a bunch of time while aiming with the mouse on the player's head until the player dies.

**RESULT** : You should immediately become a ghost.

### Bleeding to death

**SETUP** : Just have a healthy human spawn, with the AttackBodyPartByClickingIt attached. Check that the damage amount is above 0 (should be 10 to quick test it). &#x20;

**TEST :** Press F a bunch of time while aiming with the mouse on random body parts on the player.

**RESULT** : See that blood particles are spawning close to the body part you hit. Check that after a while, the player dies from lack of blood. Should take less than a minute if you hit a lot of time each body part.

### Walking when injured

**SETUP** : Just have a healthy human spawn, with the AttackBodyPartByClickingIt attached. Check that the damage amount is above 0 (should be 10 to quick test it). &#x20;

**TEST :** Press F a bunch of time while aiming with the mouse on the feet.

**RESULT** : See that player movement is slower with injured feet. Try to destroy completely the feet to see that the player cannot move anymore.

### Loosing hands

**SETUP** : Just have a healthy human spawn, with the AttackBodyPartByClickingIt attached. Check that the damage amount is above 0 (should be 10 to quick test it). &#x20;

**TEST :** Take an item in hand. Press F a bunch of time while aiming with the mouse on a hand, until you destroy it.

**RESULT** : See that a hand slot in the UI has disappeared, and that the player can't pick up items with its missing hand. Try to destroy the other one to check if the player can't take anything anymore. Check that the item held is dropped when the hand is destroyed.











