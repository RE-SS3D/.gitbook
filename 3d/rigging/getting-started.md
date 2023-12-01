# Getting Started

## Understanding the Rigging Template

The rigging template includes a myriad of clothing items that you can use as reference for creating your own.

Because clothing items aren't always worn, jumpsuits, shirts, pants, shoes, gloves, neck items, oversuits and some types of hats need secondary variants to be held and placed as items around the map.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

The reference models in the rigging template serve 3 purposes:

1. To supply modelers with a basis for articles of clothing.
2. To ensure that your hair shape keys fit within the constraints of a hat.
3. To serve as a reference for origin placement.

The Contents of the rigging template:

* Human model featuring all cutoff points and shape keys.
* References for head-worn items.
* Reference hairstyle with shape keys.
* All applicable materials.
* References for jumpsuit, gloves, and shoes.
* References for held clothing items.
* References for jumpsuit shape keys.

### Shape Keys

The reference items are not only for viewing purposes, they also serve as an example for the formatting of things such as **shape keys**. Shape keys store positions for vertices, and are used for functions such as hiding hair under hats, helmets, hoods, and masks.

<figure><img src="../../.gitbook/assets/Untitled.png" alt=""><figcaption></figcaption></figure>

You can check what shape keys an item needs by clicking the <img src="https://lh4.googleusercontent.com/B_2prMF26aDM_DAWhgtu-eWOiIfNp5cZbmhi-dc7aoTnas4x0SusOmfomLOREm-DGUNHWBT-jf4Eii_lGp4og8STeSIUXE4aNnnxQMrSqHRMv5QtBifDiW5ecC0jR1dl-BQOI3HlS6C_ek_5JJRLf04" alt="" data-size="line"> tab while any of the reference items are selected. When creating an item of the same type as one of the reference items, follow the naming convention exactly, including the order of the shape keys.

To edit shape keys on an item, simply click the desired shape key in Edit Mode, then move the vertices to the desired position as per each key.

**TIP:** You can use destructive and light constructive editing on the provided clothing items to make something new, while still maintaining clean armature weighting. However, too many changes in the geometry may result in needing to recreate shape keys.

## Understanding the Basics

This section will cover basic things you will need to know in order to progress in this guide.

<figure><img src="https://lh6.googleusercontent.com/yF-bBFJj3FQoTliL5j8Jxp7Gl6neRb2pFQhbuVnEWrsQZ7-s_7LAtTjwJdV2ZIZyaLs1Ad8yKPxU7rac45PvBUvZPOO6Pup3w_7x2iROZrrhfi-3dEclVJdYqDv_tVHOHUf3QxsX50l6yjdDY3NBETk" alt=""><figcaption></figcaption></figure>

### Rigging

To rig an item, you must select the mesh, then select the armature, and press CTRL+P. This will bring up the following menu:

<figure><img src="https://lh4.googleusercontent.com/ein306APIpY7GrIAtdFDR74YZVKVu_YgHQDNcLGwEPIyQyGUIvMbweH2qNJ0JFsjggW72anyC9jxlL_dWfY-PTtdFnPb1OLqc-NqotnrHD-aJU025dr1Lqox-xtxVOyXOx19YcVY7Mpc4iEUIjEHBu8" alt=""><figcaption></figcaption></figure>

"**Empty Groups**" creates a parenting with weights equal to zero, which is helpful for making things that are weighted to only one bone, like hats.

"**Automatic Weights**" does its best to automatically calculate which bone attaches to which vertex. Often produces undesired effects, but may be useful.

### Weighting

"Weighting" in 3D modeling refers to the amount of influence a bone has over a vertex. Typically, a weighting of 1 means "this bone has maximum influence," while a weighting of 0 means "this bone has no influence." However, more than one bone may be weighted to the same vertex.

<figure><img src="https://lh4.googleusercontent.com/t84PHgiZWS6_f3I08vU0D5c8b1739xVBTBNNdqiEaBiUdC2E6Y0LX_iHUj72WMrdOKNa9GaA-FAEPR_czQiGD54SfL0d5wmYKK_0FJPNQiLE6hW_kp1Rb1xS8GIwXfkQEKoOjYHAiBiQZeYzk2CgF-o" alt=""><figcaption><p>These vertices are weighted to the "bicep_r" bone. The warmer the color, the more influence the bone has.</p></figcaption></figure>

**You can manually set the values of vertices** to bones by clicking the <img src="https://lh4.googleusercontent.com/B_2prMF26aDM_DAWhgtu-eWOiIfNp5cZbmhi-dc7aoTnas4x0SusOmfomLOREm-DGUNHWBT-jf4Eii_lGp4og8STeSIUXE4aNnnxQMrSqHRMv5QtBifDiW5ecC0jR1dl-BQOI3HlS6C_ek_5JJRLf04" alt="" data-size="line"> button in Edit Mode, finding the desired bone in the list of vertex groups, selecting the vertices you wish to assign, then setting the weight and clicking assign.

<figure><img src="https://lh3.googleusercontent.com/0yAV4YRnPgI9bcz7XG4PR_pwthfUFfsA5jKvlxA0Y40Ge5QPMlpEMM2krME0vSgpMV0m--_fa4pMRwy2uq4tl9ar3vnAE4opgtgw2FRH-ZWtuz4BAYETwGhE5cVxSkIUXtc7MgvanL0U85IabfnEYGk" alt=""><figcaption></figcaption></figure>

