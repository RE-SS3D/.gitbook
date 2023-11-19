# View

A <mark style="color:purple;">**view**</mark> is a controller for an user interface, it sets the parameters, controls buttons, etc. A view's existence is never known by [<mark style="color:purple;">**systems**</mark>](system.md).

```
public sealed class RoundTimeView : Actor 
{
    // add time logic
}
```

If we need to network a view, we can either use a direct call on a [<mark style="color:purple;">**system**</mark>](view.md#system) or use [<mark style="color:purple;">**network messages**</mark>](../../networking/fishnet-networking/network-message.md). Do not use the [<mark style="color:purple;">**event bus's events**</mark>](events/event-bus.md) for that.



## <mark style="color:yellow;">**⚠️**</mark> <mark style="color:red;">**IMPORTANT!**</mark>

Always add the postfix "**View**" in the name of the <mark style="color:blue;">**class**</mark> for your <mark style="color:purple;">**views**</mark>.

