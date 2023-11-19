# Ranged

**RANGED**

Holding RIGHT\_CLICK, while having a ranged weapon in an active hand, will make player character to aim at the cursor.

<figure><img src="https://lh3.googleusercontent.com/oUxKDztcPz39yf2P55y-3cQS4ofmlowfui7jJLLkVs2HEvDKE3EMv9S-JpO2K6uxBdu1-zD3ubjnjuNr-KC2683ICKmWndKNkj5jmoK27sahHJEX4qBLa_OrUZXcRFdWRioE__YIF8ZbubW7zEIjNw" alt=""><figcaption><p>Aiming for the wall deliberately.</p></figcaption></figure>

The character should follow their aim at the location cursor points at freely, until it points at the target (human or other living being that has individual parts that can be aimed at).

If cursor overlapses with the target, the aim of the character must automatically lock on and aim at the middle of the bodypart of the target, that was selected on the UI dummy.

<figure><img src="https://lh3.googleusercontent.com/WgDO5oNcVHoVAvQLsBbGExP9Tif1MLcbawXqclRMeuorPBIJWfdiHFVMh2gwik4AWIvdkdr7YcbZaDLZJLAbiYkr7yIgWyrhWsKwcDBszr0GOuHiVn8xlT1pyfuN-qe2JMcitCnq4Z9VfC5JzQLWEQ" alt=""><figcaption><p>Aim is automatically taken to the selected bodypart.</p></figcaption></figure>

Aim (and the animation of the aim via IK, probably) should change if the targeted bodypart on the dummy was changed via hotkeys.

<figure><img src="https://lh6.googleusercontent.com/Ef-HBs-Drj8ZjznaeNIUWbtWvG0oqaYMW_V3ngsRw85UX4HZo1P50GoLKJ_nWeLzaDHPzDIHq0z2Vn88ExxG1U9bPEHExSnIfYUyU7wU_TOhNQcN0nvC5uvO2WLXgOC8wJGtu68d3UR01S9uL7gbuA" alt=""><figcaption><p>Aiming for the eyes.</p></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/WHA4zE_sL-5NkDAdsR4uG3ChTl1Dy2sHyxqPY-UhQnpgbpeyvIwnRc0F7IrAPBTxttVeiWv0GS5wLb0nDhqZuvDPmMLTS5Nj-Qp_L-zqaw671pioDt17p1FGp7B6yzWslv2mFfrRyLLwjAFPgV2IaA" alt=""><figcaption><p>Aiming for a hand</p></figcaption></figure>

In case the part of the character that is currently aimed at is obstructed, the aim on the UI dummy should be disregarded and the aim should remain “free” as in unlocked from the target and should simply follow the cursor.

<figure><img src="https://lh3.googleusercontent.com/SPYKOcBfgpbOdRAbAVvx7Zwb3BHt3KFAVGPFVEYNdi8tmunhUSrjslc90uWuE5lsimMLE-l75tZysPGEu5DmCYB7ToxDSNrUn7UdAJVIcR7eiok9lZLHh0p84I7aUFwHAcD7w53v4Qwk5g6zfBYMZA" alt=""><figcaption><p>The target bodypart is obstructed, so the aim is taken at whatever the coursor is pointing at.</p></figcaption></figure>

If the said part of the character is no longer obstructed while the “free aim” is still on the targeted character, it should remain that way to prevent aim jumping. To re-aim and lock onto the targeted bodypart, cursor must be moved from the target character and then moved onto it again.

LEFT\_CLICK while having a ranged weapon in an active hand AND aiming (holding RIGHT\_CLICK) should make the gun shoot in the direction of the current aim, free or not.&#x20;

There should also be a chance to miss the body part that is aimed at within a certain radius (represented by the transparent red circle on the image below) or even miss the character entirely.

This error radius should depend on:

·         type and integrity of the weapon

·         condition of the aiming character’s body (especially the arm holding the weapon)

·         other effects on the aiming character, such as medication, drugs, alcohol or other

\- Distance between characters

<figure><img src="https://lh6.googleusercontent.com/6bvVEdr4kelV72LIyQ6WBD3A3yLrA9bchnSebhoWx1fkfrAec6GseWSh7ATXN8SGIDyJo-MhZPiciyvYRbcYNL7cb--81YdK0TmZ5uOBbZjsTDJwdtZROJmGBzw7FrlMekLR2v5yAanwNSNOh2ZSyA" alt=""><figcaption><p>A cone of possible directions to miss while shooting.</p></figcaption></figure>

Once the point of the shot is established aiming should be locked (player should still be able to move the cursor), the animation of the fired shot should play for the character, damage and force of the shot should apply to the target. After that, the aiming process should continue as normal.

In case of the automatic weapons or other weapons that fire continuously, established aiming should not be locked, but should remain “free” from the point of starting fire (both time and aim coordinates). For example, longer LEFT\_CLICK while aiming at target’s chest with a flamethrower should result in continuous fire in the general direction of the target’s chest, but

LEFT\_CLICK while having a ranged weapon in an active hand will make player character shoot from-the-hip style, aiming rules above applied.

LEFT\_CLICK on an active target character, while having a ranged weapon in an active hand AND aiming (holding RIGHT\_CLICK), will make the player character shoot, aiming at the targeted area.
