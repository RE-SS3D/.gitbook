# SubSystem

{% hint style="info" %}
This refers to a technical concept, not as a generic "container subsystem" or a "interactions subsystem"
{% endhint %}

A subsystem is a <mark style="color:blue;">**class**</mark> that manages something, it should work on its own, the only exception is when it needs information about other subsystems, but it is preferable that you do that by using <mark style="color:purple;">**events**</mark>, <mark style="color:purple;">**event buses**</mark>, or [<mark style="color:purple;">**network messages**</mark>](../../networking/fishnet-networking/network-message.md).

A subsystem can be networked or not, for that you can inherit your class from <mark style="color:purple;">**SubSystem**</mark> or <mark style="color:purple;">**NetworkSubSystem**</mark>.

Here's a snipped of how you can declare a subsystem that creates an explosion somewhere.

```
public sealed class ExplosionSubSystem : NetworkSubSystem 
{
    public void CreateExplosionAt(Vector3 position, float size) 
    {
        // boom.
    }
}
```

It is also important that you know how all the subsystems work with the [<mark style="color:purple;">**SubSystems**</mark>](subsystem-locator.md) <mark style="color:blue;">**class**</mark>

{% hint style="warning" %}
Always add the postfix "**SubSystem**" in the name of the <mark style="color:blue;">**class**</mark> for your <mark style="color:purple;">**subsystems**</mark>.
{% endhint %}
