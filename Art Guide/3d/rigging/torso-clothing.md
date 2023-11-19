# Torso Clothing

{% hint style="info" %}
## Difficulty: <mark style="color:orange;">Moderate</mark>
{% endhint %}

To beginners, this may be the first part of the guide where you may need to do extensive weight painting. If this sounds like you, you may want to brush up on techniques by checking out YouTube tutorials on weight painting, or by asking fellow SS3D model creators.

### Methods

**There are two key methods for creating torso clothing for SS3D characters:**

First is just by editing the reference items and maintaining the weights that way. You can find some tips for this method by checking out the Basic Clothing section of this guide on page 5.

The second method is by creating your own model from scratch, then by **transferring the weights** from the model in the rigging template named "Human Weight Transfer Model." In order to transfer weights from one mesh to another, follow these steps:

1. Parent your mesh to the rig with empty vertex groups.
2. Add a Data Transfer modifier to your article of clothing.
3. In the modifier, select the eyedropper and select the object you want to transfer the weights from, then toggle "Vertex Data."
4. Select the drop down in the top right of the modifier and click "apply."

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption><p>This is where the magic happens.</p></figcaption></figure>
