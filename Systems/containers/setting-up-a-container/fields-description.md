---
description: >-
  This page explain what the fields in the AttachedContainer script are doing,
  and eventually what you have to do to set them up correctly.
---

# Fields description

### AutomaticContainerSetUp

The ContainerDescriptor has a custom editor, when checking this checkbox, the custom editor will handle adding necessary scripts, as well as showing you only relevant fields.

99% of the time, you want to check it. The only time you don't want to check it is when for some reasons you want your container scripts spread around multiple game objects, which should be the exception.

### **ContainerName**

This is the <mark style="color:blue;">name</mark> that will appear in interactions, such as "store in <mark style="color:blue;">toolbox</mark>".

It's also useful to distinguish between multiple containers on the same game object.

### IsInteractive

Checkbox to define if the container can be interacted with. For most containers, that should be the case.&#x20;

### HasUI

Define if the container needs an UI or not. If not, the "view interaction" won't be available, only the "store" and "take first" interactions.&#x20;

### IsOpenable

Define if the container has a open/close interaction, or not.

### OnlyStoreWhenOpen

If a container is openable, then this defines if the container needs to be open to store anything in it. It should be checked for most openable containers but it's there as they could be some exceptions.&#x20;

### HasCustomInteraction

You might want your container to behave in an exotic fashion, with particular interactions. If you check this one, you have to add a script on the gameObject implementing InteractionTargetNetworkBehaviour's interface, otherwise you won't be able to interact with your container.

### MaxDistance

This set up the maximum distance between the user and the container before the UI closes. Only available if HasUI is checked.

### Size&#x20;

This is the size of the container. It represents the number of slots in a rectangle grid, the first number being the width, the second the height.

### HideItems

Set if items should be invisible (not rendered) when inside the container. There's a few cases where we'd like items to be rendered, such as when they are inside a locker.

### AttachItems

Set if items should become childs of the container game object when inside the container. In most case you should leave that checked.

### Filter

A global filter on the container, allowing you to decide what kind of items can fit in it.
