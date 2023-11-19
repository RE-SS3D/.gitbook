---
description: The red stuff swelling inside.
---

# Blood

## What's blood for? <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

Blood is circulating through the body, carrying oxygen, it's necessary for body parts that require oxygen.

The hazard players are most likely to face, likely result in some form of bleeding.

Many creatures you’ll encounter also rely on their blood levels to survive. In the average human’s body, all players start with around five liters of blood. **Any attack with a sharp object, like a broken bottle, or a kinetic firearm, may form an open wound that causes blood loss relative to the severity of the wound.**&#x20;

Luckily, most living things (humans especially) are equipped with processes that slowly reduce the severity of most wounds, meaning blood loss will slow down and eventually stop. However, some wounds may be too severe, and cause fatal blood loss faster than the wounds can be naturally healed. A little blood loss is one thing, but a lot of blood loss is another thing.&#x20;

## Blood volume in the body

A human with an average body contains around 5 liters of blood, so if a human has an approximate volume of 65L, we have a ratio of approximately 0.077, blood on total volume. Applying this ratio to individual body parts we can deduce their blood volume (always assuming that blood is spreaded homogeneously in the body). Let's call B a body part and BV its blood volume, then :

$$BV(B) = \text{Vol(B)} \times 0.077$$

The blood a human can contain can be should then have a maximum volume capacity roughly equal to the sum of individual body parts blood volume. let's call this substance container volume $Vol(S\_c)$, then

$$Vol(S_c) = \sum_i BV(B_i)$$

This simple formula will be used to always determinated the maximum amount of blood a human can contain, depending on what limb they have left.

This quantity will change if the player lost a limb, or any other parts. It is important because it can help to define the right amount of blood the player needs to have in its circulatory system, and it's drastically different if it's a whole healthy human or just a living head.



<div align="left">

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption><p>Blood maximum volume is represented by the black rectangle, blood volume in the player is represented by the red area. The severed head on the right is going better than the player on the left, it contains proportionnaly more blood .. until oxygen runs out. (Note that blood max volume proportions are not on scale, head should be only about 1/13 of full body) </p></figcaption></figure>

</div>

## Absence of blood, global effects

Below is a chart of blood levels, and how they affect the player.

As a player can lost limbs, or even just be a brain, the player does not need the same amount of blood depending on its total volume.

Keep in mind the percentage below is expressing the amount of blood in the body, over the maximum amount of blood that could be in it.

<table><thead><tr><th width="156">Units of Blood</th><th width="385">Effect</th></tr></thead><tbody><tr><td> 100%</td><td>No ill effects.</td></tr><tr><td>80-100%</td><td>Low chance of dizziness.</td></tr><tr><td>60-80%</td><td>High chance of dizziness.</td></tr><tr><td>40-60%</td><td>High chance of dizziness, slowed movement speed, player may randomly be stunned or pass out.</td></tr><tr><td>20-40%</td><td>High chance for dizziness, slowed movement speed, player may frequently be stunned or pass out.</td></tr><tr><td>0-20%</td><td>High chance for dizziness, slowed movement speed, frequent stuns and passing out. </td></tr></tbody></table>

Other effects, such as vision reduction may apply.



## Absence of blood, local effects

Blood is essential to convey oxygen. If blood lacks too much, then oxygen starts to be difficult to conveys to organs and other body parts. This inexorably lead to oxygen damages.&#x20;

Oxygen damage can eventually lead to body parts failing and dying, see more in :

{% content-ref url="organs/" %}
[organs](organs/)
{% endcontent-ref %}

## Treating blood loss

Open wounds may be treated using medicines, just like most other injuries. Cauterization is also a potential solution, as well as bandages and sutures.

Because the amount of blood loss from open wounds needs to be tracked, each limb may need to track their own contained blood and wounds.&#x20;

That said, bleeding damage shouldn’t be counted toward the total damage taken by a player, and instead should simply be an indicator of how much blood is being lost over time.

Blood can be drawn and injected with syringes and IV drips, can be lost from wounds and regenerated through chemicals. Blood regenerates slowly over time, and regenerates faster the better fed the character is.

There are also blood types, which follow the general real world rules. Lizardpeople have a special bloodtype, marked L, which can only receive from and donate to the L blood type. See&#x20;

<figure><img src="https://lh5.googleusercontent.com/tREF0-zKyxtqORbKOH9qCrYG-THqAfGTrh-mx0SPuTh_B_TtY9oUG39iNImrFsrUucq3hLXnlnjJCtuJUyfScuk5wqPJu-IjVtiBzJObEWh7PaaA6IiRBnuje3K1sK8VnEcfbxiv4f6MgcmNfsve9Q" alt=""><figcaption><p>Blood types compatibility table. Indicates which blood types can receive which. Red is the donor.</p></figcaption></figure>
