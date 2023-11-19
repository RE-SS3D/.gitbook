# Head Items

{% hint style="info" %}
## Difficulty: <mark style="color:green;">Very Easy</mark>
{% endhint %}

Given that head items almost always need to be weighted only to the head, this is the simplest type of cosmetic item to add, and is very beginner-friendly.

### Hair & Hat Interactions

When modeling a head item, you may want to take a peek at the supplied hair models within the rigging guide. Given that hair and hats both need to fit on a player's head, **hair needs to change its shape depending on the hat.**

As such, **hairstyles have four possible shape keys: hats, helmets, masks, and hoods**. For helmets that cover the entire head, like hardsuit helmets, the hair may be hidden entirely.

When designing a head item, you may want to enable the desired hair shape key and design around it.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

### Rigging Head Items

The majority of head items (aside from things like hoods or hats with dangly bits) can be weighted entirely to the head bone. To do this, make sure the hat is parented to the armature with empty vertex groups, then in edit mode, **select all vertices and assign 1.000 weight in the** <img src="https://lh4.googleusercontent.com/B_2prMF26aDM_DAWhgtu-eWOiIfNp5cZbmhi-dc7aoTnas4x0SusOmfomLOREm-DGUNHWBT-jf4Eii_lGp4og8STeSIUXE4aNnnxQMrSqHRMv5QtBifDiW5ecC0jR1dl-BQOI3HlS6C_ek_5JJRLf04" alt="" data-size="line"> **tab.**

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption><p>Set the vertex groups tab like so and press assign after selecting all vertices in your head</p></figcaption></figure>

After you're done, consider whether your hat needs a held variant based on the type of head item you created.
