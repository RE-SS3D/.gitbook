# Surgery

## Surgical Access

Several problems require immediate surgery to save the patient, some of which concern their extremities or internal organs, in which case the patient must be "opened" in order to directly interact with the part that needs doctor's attention. The overall organ access order (by body parts) should look as such:

<figure><img src="https://lh4.googleusercontent.com/yRYSWuDjF8YhoE_W8frobnbWsckMZdmw5-NlwgBuj2pSKIthGONWzVz9kPUktfwaVsoia-mJdgiGxJg8zWGgpsoHDbrNv7L1nwH7myklmP58Nef1827KKSaJ5LxQk_P2gP6fSnrVm2LoLcg-sJvDIQ" alt=""><figcaption><p>Head access</p></figcaption></figure>

That means, while Eyes, Ears and Speech organs (Tongue) can be directly accessed and treated without surgical intervention, to treat the brain the doctor should first cut through the skin of the patient’s head and through the skull bone. Or, in other words, they should cut through the MUSCLES and BONES layers of the Head body part.

<figure><img src="https://lh6.googleusercontent.com/ABNOXlGlfNO0j1XjmR4Vzw9tizG8Awkf9LDUYH5uccbG2KAAgTBActn7Ev615rJIRX5ER0UztaNATU0uzpS8u1KoeL8jjLqr-XAdJDdWtoAErzJxlCpm1sqm-SxHpdY43FE_pd1xf2AiwfbMPUGK_w" alt=""><figcaption><p>Torso access</p></figcaption></figure>

The dotted line means that there’s no need in any sort of incisions to access the needed organ, the parent organ just should be moved (Made for simplicity and cartoonish style, don’t try this at home, author knows nothing of real anatomy or surgery or medicine in general. Applicable to the whole document, actually.)\


<figure><img src="https://lh3.googleusercontent.com/_ED87nrog1dPnEoldYu4ToDvzXSq_lRvldLsNQlvKT4Da2NlOIsDjozN-knTLdHLWtzWOsFFS_mZBG4rkgRrfFQirdkhjON5jNzrVCKfIQnVnXyIUM9vX8OgV6YqfjdWN9U_gKVT3GaOOKzy8ihdvw" alt=""><figcaption><p>Limbs access</p></figcaption></figure>

## Surgical transplantation

In order to be removed, the organs should be surgically accessed and disconnected from MUSCLES, CIRCULATORY and NERVES of their body part.

Example: In order to extract the brain, the doctor should first cut off the top of the head, open the skull, cut the nerve endings, cut off (and cauterize, depending on the situation) the blood vessels and extract the brain. In order to install a different brain in it’s place, the doctor should basically perform the procedure in reverse: place the brain in the head, reconnect blood vessels of the new brain and the body, reconnect the nerves, close the skull and staple the head back.

## Surgical tools

Surgeon uses a variety of tools&#x20;

* Tools for incisions (TI) - the tools to cut through the soft tissues of the organism, used primarily on MUSCLES, CIRCULATORY, NERVES and ORGANS. The most convenient one is Scalpel, but any item/weapon that can do slash damage might work (the more the characteristics of the item differ from the scalpel, the worse it is as a tool for surgery, i.e. being too heavy, making too much/not enough slash damage, etc.).
* Tools for bone cutting (TBC) - tools to cut BONES. Bone-saw is an obvious choice, but other types of slash damage items might work (but even worse than the incision tools).
* Tools for retraction (TR) - opens the incisions wide, holds the skin and MUSCLES in place and doesn't allow it to close on the doctor while they operate. Surgical retractors are made for this purpose, but wire-cutters or wrench can be used in case of emergencies.
* Tools for cauterizing (TC) - burns the CIRCULATORY to stop blood loss from a specific vessel, for example, after ORGAN removal. Cautery is the choice for this job, but any item that can provide a similar HEAT damage can possibly work.
* Tools for manipulation (TM) - for moving organs tissues and bones around without harm for the patient. Might also be used to close the CIRCULATORY vessels (to be reconnected later). Hemostat is the intended tool, but wire-cutters can be used to achieve the same effect with a certain chance of failure.
* Tools for bone merging (TBM) - for setting BONES back together after fracture of surgical procedures. Bone gel can make bone tissue ductile, after which the bone parts can be mended back together with TM, but it can be partially substituted with surgical tape or a regular adhesive material for worse results.
* Tools for wound closing (TWC) - for sawing MUSCLES wounds back together or bandaging the wound. Depending on the severity of the wound/incision, medical gauze or surgical tape might be enough, but the wound might reopen if the application is removed too early. Surgical suture is more time consuming and works only for incisions, but needs no removal. There are ghetto versions for both, being adhesive tape and cloth for the first option and regular sewing thread or wire for the second.
* Tools for drilling (TD) - for making holes in BONES or teeth to insert pills/patches into a resulting cavity. The medical drill can be used for it, but the cavity can also be dug with other drills like mining one (why) or meticulously scratched using needles or scalpel.

### Surgical description (in-system)

Surgical operations should be described in the same way as basic crafting recipes (see [Crafting Design Document (WIP)](https://docs.google.com/document/d/1ZfYrOXdwH0Zn3isCIHe5zT4pGxnJCUlri4wJjcA4jWU/edit#heading=h.y3rbe862ehzj)), in a sense that every interaction of the tool with a certain layer or organ should describe the target, the tool and the result of the basic interaction.

```
{
  "type": "surgery",
  "result": " [ { "bones_access", 1 } ]
  "time": "10 s",
  "tool": "saw_circ",
  "component": [ [ [ "head", "bones", "bones_access", 0, "muscles_access", 1 ] ] ]
} 
```

This “recipe” describes that if a circular saw is used on a patient head’s skull when the skin in the head is already cut, then after this interaction 10 seconds (of animation) should pass and  the skull would also be opened.
