# Interactions Guide

### Creating a new type of interaction

Figure out if you want the interaction to be on a target (ex. machine in the world) or on a source (item in hand, ex. welder, crowbar) which interacts with a different target. Once you have worked out if it is a target or source, create a class which implements IInteraction. The most important methods are going to be:

* GetName: generates a display name
* CanInteract: if the interaction is possible
* Start: called when the interaction is started

You can access data about the interaction using the InteractionEvent parameter. I recommend looking at existing interactions for examples.

### Making an object interactable

Add a script to the object. It should inherit from InteractionTargetBehaviour or InteractionTargetNetworkBehaviour, depending on if you want certain things to be networked. You will have to implement GenerateInteractions in your class. There you can return an array of the interactions on your object.

### Creating an unique interaction for an object

If you are creating an interaction which is only needed for a single kind of object, consider using a simple interaction. You can create it and assign callbacks which you can directly implement in your attached script.

### Adding functionality to an item

The item component is the source of the interaction. To add more interactions, you can add a component which implements IInteractionSourceExtension.

### Help! I'm stuck

Send Alainx277 or John a message on the discord, we'd be glad to help
