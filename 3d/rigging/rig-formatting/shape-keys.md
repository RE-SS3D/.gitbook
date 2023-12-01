# Shape Keys

A shape key (also referred to as "_blend shapes_") is a basic mesh transformation that moves vertices directly from point-A to point-B.&#x20;

<figure><img src="https://lh5.googleusercontent.com/TmUKHbydk7V2KE0-3_mZed5Xh-6udEdHn88LYAd5QP-jbx4VCiz_IlajTPeHPlcGS74r49gSt0UDDw5KiZws_7OijeeuzfKlD_bj5JRA_mrspLdznyK-CVnla9JOEjwpx4jiAE4u1Tc4UO5dwnOtxYc" alt=""><figcaption><p>Location of shape keys in Blender.</p></figcaption></figure>

### Body Shape Keys

Shape keys can be used for a variety of functions, but in this context, we use them to customize the proportions of player-created characters.

Accordingly, the rigged clothes need to be able to support the shape of the body underneath, so clothing items also need to contain the same shape keys.

**The shape keys that need to be accounted are as follows, and need to be named exactly the same way:**

* **Basis** - The default character shape.
* **Female** - The female variant of the base character.
* **Breasts** - Size of the bust.
* **Fat** - Chubbiness.
* **Muscle** - The size of the character's muscles.

<figure><img src="https://lh6.googleusercontent.com/PekSchO3rwFB2ztfu6Qx1iZME8Oox2O6d5TAn3CKV9q4eRO3v_1HpJcEIryK1IoF5nvYJwwHdn64q5QnQj5-WuvLwnpZ4hglKKF7vz2V-pD9gtihyMHKGuIifHP8wfj0YAtJs4DcR0ij482ahmlRy0g" alt=""><figcaption><p>Basis vs. Muscle keys.</p></figcaption></figure>

### Hair Shape Keys

While body shape keys are used for customization, hair shape keys are used to maintain the look of the character while also allowing hats, helmets, masks, and hoods to be worn on top.

For this, we shrink the effected part of the hair so it fits within the constraints of the hat. For this, I've created a couple shape keys that should fit the constraints of a large majority of hats.

**The shape keys that need to be accounted are as follows, and need to be named exactly the same way:**

* **Hat** - Squishes the top of the hair down as if there were a hat on top.
* **Helmet** - Squishes all sides of the hair inward toward the head aside from the bangs. Used primarily in instances where the helmet might reveal a lot of the head.
* **Mask** - Squishes the bangs inward as if a mask were pressed against the face.
* **Hood** - Like the Helmet shape key, but more extreme.

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>
