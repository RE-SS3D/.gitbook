# Hairstyles

{% hint style="info" %}
## Difficulty: <mark style="color:orange;">Moderate</mark>
{% endhint %}

Hairstyles are among the most in-demand cosmetic types, being one of the most ground-level customization options for players. Provided you're able to model some decent-looking hair, the rigging process for hairstyles is similar to hats, with a bit more work.

### Rigging Hair

Hair is easy to rig, provided you don't need the hair to move off the head (like a ponytail swishing around.)

**To rig most types of hair, you can simply follow the guide on the** [**head items page**](head-items.md)**.**

If you need to add bones to make the hair move, you can edit the default rig to include those bones. Adding bones named hair1, hair2, hair3, etc. and weighting them in Blender is enough -- dynamic bones are applied in Unity, if used.

### **Shape Keys**

Hair utilizes shape keys to allow it to fit inside headwear. When making hairstyles, use the reference hat, helmet, mask and hood to create the respective shape keys.

(When making the Helmet key, only use the "Reference Helmet 1". "Reference Helmet 2" is an example of an item that would hide the hair completely in-game.)

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Feel free to check out the provided hair models to see how the shape keys look.</p></figcaption></figure>
