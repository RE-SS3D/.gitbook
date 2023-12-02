# Custom storage conditions

It's possible to add custom storage conditions to a container. Those conditions allows you to extend container ability to remove or add items, based on pretty much anything you want.

To do so, you'll need to create a new script that implements the IStorageCondition interface.

Here's an example :&#x20;

```csharp
public class JumpsuitStorageCondition : Actor, IStorageCondition
{
    [SerializeField]
    private AttachedContainer _beltContainer;
    public bool CanRemove(AttachedContainer container, Item item)
    {
        return _beltContainer.Empty;
    }

    public bool CanStore(AttachedContainer container, Item item)
    {
        return true;
    }
}
```

This condition is for the jumpsuit container on the Human. It allows the jumpsuit to be removed only if the belt container is empty. Pretty simple !&#x20;

Just put the condition script on the same game object as your container, you can add multiple conditions if you want.

<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

