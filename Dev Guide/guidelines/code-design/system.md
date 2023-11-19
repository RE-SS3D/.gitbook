# System

{% hint style="info" %}
This refers to a technical concept, not as a generic "container system" or a "interactions system"
{% endhint %}

A system is a <mark style="color:blue;">**class**</mark> that manages something, it should work on its own, the only exception is when it needs information about other system, but it is preferable that you do that by using <mark style="color:purple;">**events**</mark> or <mark style="color:purple;">**event buses**</mark> or [<mark style="color:purple;">**network messages**</mark>](../../networking/fishnet-networking/network-message.md).

A system can be networked or not, for that you can inherit your class from <mark style="color:purple;">**System**</mark> or <mark style="color:purple;">**NetworkSystem**</mark>.

Here's a snipped of now you can declare a system that creates explosion somewhere.

```
public sealed class ExplosionSystem : NetworkSystem 
{
    public void CreateExplosionAt(Vector3 position, float size) 
    {
        // boom.
    }
}
```

It is also important that you know all the systems work with the [<mark style="color:purple;">**SystemLocator**</mark>](system-locator.md) <mark style="color:blue;">**class**</mark>

{% hint style="warning" %}
Always add the postfix "**System**" in the name of the <mark style="color:blue;">**class**</mark> for your <mark style="color:purple;">**systems**</mark>.
{% endhint %}
