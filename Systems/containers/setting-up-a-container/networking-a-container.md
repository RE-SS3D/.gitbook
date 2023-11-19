# Networking a container

Container's content should not be easily visible to just anybody. We're using Fishnet's solution to limit visibility of some game objects to some clients.

If your container's content should be only accessed by client "viewing it", meaning they used the view interaction on the container (it'll be this case for most containers), then here's how to proceed.

First, make sure your AttachedContainer script is on its own gameObject. This is because fishnet will make the game object invisible to most clients, but we only want the container to be invisible, not the other component of the game object. You can add a Container gameObject as an example :&#x20;

![](<../../.gitbook/assets/image (28).png>)



Now add a NetworkObserver script on this gameObject, check override type as "Add missing" (unless you have a specific reason not to do so), and add a ContainerViewedCondition on it :&#x20;

![](<../../.gitbook/assets/image (49).png>)

Make sure the containerInteractive script is not on the same gameObject, otherwise interactions won't be available to the client. It should be up in the hierarchy, in our example, we could put it on ToolBoxBlue.

That container should be ready to go, and networked as expected !
