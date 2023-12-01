---
description: Direct stuff where it needs to be.
---

# Toss and Throw

TOSS/THROW

Holding CTRL+RIGHT\_CLICK while having an item in hand or holding a target character in a grab, will result in the player character preparing a throw. An arch-like trajectory indicator should appear and follow the cursor, indicating the supposed trajectory of the thrown object, where landing point ending where cursor points. (Works <mark style="color:blue;">regardless</mark> of the player's current combat mode.)

{% hint style="warning" %}
Warning: might be too OP. In that case, the trajectory trail should be either disabled or become more transparent the greater the distance to the intended target.
{% endhint %}

<figure><img src="https://lh4.googleusercontent.com/Tctuje0Ta_Fr6wLPq6xfKqRjVY6KuyPQ1ckT2RB2H53xH9chBtxwr-WSgDvjU8pSMF3PuPFRMr484rhZ8ig5NTtw96wVh-rd_8LUVW5x5bK98YvwdEac6YnrhD-L90duwDP1EK5SIY_62oRe3d8rjw" alt=""><figcaption><p>Aiming for the floor with a bottle.</p></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/m6EeMZ0ftN8Jwe8rjjUY5JPiSOTZBZIEf5qbZ2kHOAattraa9oy3uT5n4lKrqRS9QWQPxQ6hCYXZ-IiF5KtwvDfrD0QBqTkGlUahQlY5dy03Vu7T7fcI0JseQaIN5UznjSH5HUrBzWYxKCSzwsOlOw" alt=""><figcaption><p>Aiming for the wall with a bottle.</p></figcaption></figure>

Suggestion: trajectory indicator should fade away the longer distance a thrown object should travel if thrown, as bounce prediction over long distances might be too OP. Alternatively, it can be only visible with an item perk, like AR glasses (if anybody would use them)

While aiming at the active target character, while having an item in hand and if Combat mode is <mark style="color:red;">enabled</mark>, trajectory indicator should “stick” to the bodypart of the target, selected in the UI dummy.

<figure><img src="https://lh6.googleusercontent.com/aRcLc6iEI4iVoVqdrmfSmVOYbVj7P2PVV9I_tPASqDUCCQ0PvMdbIp5uUVhjcqwQlnSysrS76ZAEthAHmlrqVlcoo5vUKsup287nHJazOfIIjL-jEKGvQcoMO0CLan5gAZPitZJa2itU9JLjwEJubA" alt=""><figcaption><p>The trajectory automatically switches to the selected bodypart of the target.</p></figcaption></figure>

(If Combat mode is <mark style="color:green;">disabled</mark>, indicator should treat other characters no different from other environment entities (no “auto aim” at the characters))

LEFT\_CLICK while aiming on an active target character, while having an item in hand and Combat mode is <mark style="color:red;">enabled</mark>, will result in throwing the item in the active hand at the target character.

<figure><img src="https://lh5.googleusercontent.com/TRiTh0NrjYMUOY6RdJpqX3Zd9Crm42mie9vmzpzV_4e3Ceh-CKEzGqy6FPBnzvPQ7JU5-jZGDX40Ubylcdfj5EYhcmzJuQPa_lmH7owEcULyPxbpuz4UlVimAva8umqkmFyKO-AfU_Lycj6-rpud9A" alt=""><figcaption><p>The moment of impact.</p></figcaption></figure>

The damage of the item, shall it hit the target, should be calculated from the weight of the item + it’s perks (to decide the damage type, for example \*sharp\* should result in dealing a certain amount of SLASH damage) + health and stamina conditions, as stated in the HARM section. If Combat mode is <mark style="color:green;">disabled</mark>, LEFT\_CLICK will result in tossing the item in the active hand, dealing no damage (or less damage then when throwing)

LEFT\_CLICK while aiming anywhere in the gameworld while holding an item, will result in throwing the item at the cursor.

(Works <mark style="color:blue;">regardless</mark> of the player's current mode.) (Holding a target character in a grab should throw the target character’s ragdoll in the general direction of the cursor) (Can be used to toss grenades: activate the grenade and toss it in the direction of the target.)

<figure><img src="https://lh6.googleusercontent.com/qop5Kxsyf4U031JsdYwHlqDQRvUybmw5lSg04J5yxwA3rGpUU70Pnz9UCYBehIa3pRb3UAEmZvEll9E22LbCkHAiHnuAK_cUL0lunKiDqErSU3xTcgFMr6OcynlAUuOHSvC5G6AKxdd0nZR3IvcmvA" alt=""><figcaption><p>Works the same way with ragdols: point at the place...</p></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/C31rA6xUv4oaz8-np_GvqRIOdZ3_H1QWKtOhx8_PzuNaaXMZy8M-ZvTHj-Uoi6mbCvz6X3xo52UDLPhtXn-Vy32WMmdEyl9qwKRmoLvWA20eT8MT23dwwYgtY9VNrQoKLZCBvJFHPyJW4sBh0vbvmw" alt=""><figcaption><p>...and throw.</p></figcaption></figure>
