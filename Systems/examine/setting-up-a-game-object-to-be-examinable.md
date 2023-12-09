# Setting up a game object to be examinable

To make an object examinable, you'll need to add at least two scripts to it. Selectable.cs, which will allow the Selection system to pickup the object. SimpleExaminable.cs, which will allow to give a name and a description to the object.&#x20;

SimpleExaminable ask for a scriptableObject, you'll need to create it in Assets\Content\Data\Examine\String. For that you can right click in Project and choose Examine. You can then add a reference to the newly created asset in the examinable object.



<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption><p>The two necessary scripts to make a game object examinable</p></figcaption></figure>
