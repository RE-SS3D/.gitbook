---
description: >-
  This page describe how one can set up a container on a game object in the
  Unity's editor.
---

# Setting up a container

The first thing you need when setting up a container is to add an AttachedContainer script on your game object.

This script has a custom editor that will allow you to build a container in a coherent manner. The AttachedContainer also contains references towards other relevant container related scripts, such as ContainerUI, Container and others.

Once AttachedContainer is added, you should see a pretty confusing editor, looking something like this :&#x20;

![](<../../.gitbook/assets/image (19).png>)

If you're unsure what all this stuff does, just check the Automatic Container Set Up checkbox. It will tidy up the editor as well as set up a bunch of container related scripts automatically.

![](<../../.gitbook/assets/image (22).png>)

After checking the box, it should look like this. With Automatic Container Set Up checked, you can mess around with the editor since it's designed to avoid any incompatibilities. Changing some values may remove or add some other fields.

![](<../../.gitbook/assets/image (17).png>)

This will also add to your game object the necessary components to make your container functional.

![](<../../.gitbook/assets/image (18).png>)

There's a tool-tip for each field, so just hover your mouse on a field to know more about it.

![](<../../.gitbook/assets/image (4).png>)

