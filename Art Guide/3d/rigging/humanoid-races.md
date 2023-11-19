# Humanoid Races

{% hint style="info" %}
## Difficulty: <mark style="color:red;">Hard</mark>
{% endhint %}

_**This section and beyond is incomplete until precedent is set for such things. In the meantime, here are some key points:**_

### Humanoids

• When making models based off the human rig, try to avoid making them thicker than the human model. This is to ensure human clothes fit.

• If making a non-humanoid rig, please be aware that there is no current standard. If you are going to attempt to create a new standard, consider the following:

* Rigs with altered lower-bodies (like digitigrade legs) may reuse much of the human upper-body. This should expedite the conversion of existing clothes to your new species.
* Clothes for new races do not need any new item variants for clothing, provided they are based on an already existing outfit.
* If you are establishing a new standard rig, be keenly aware that you will also likely need to create new animations to accommodate.

• Analogues to hair on new races (like antennae or lizard frills) may also need to have shape keys similarly to human hair, otherwise your lizard frills will probably clip through a helmet or two.

• If your race's limbs are severable you will of course need to make severable limbs. To do this without having visible seams, you can copy the normals from the completed version of your race's body mesh.\
To copy normals, overlap the severed version and the completed version, and apply a **Data Transfer** modifier to your severed version.\
Then, check "**Face Corner Data**", select "**Custom Normals**", and set **Mapping** to "**Nearest Corner of Nearest Face**".\
Then, make the Source of the data transfer your completed body, and then apply the modifier. You will need to do this for each of the body parts. You can do it all at once by slapping all of the severed limbs into one object, and seperating them into individual parts after you've applied the modifier.

<figure><img src="../../.gitbook/assets/Untitled (2).png" alt=""><figcaption></figcaption></figure>
