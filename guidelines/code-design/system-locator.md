---
description: >-
  Class used to get game systems, using generics and then making cache of said
  systems.
---

# System Locator

The <mark style="color:purple;">**SystemLocator**</mark> is a class used to easily find any system that has been registered on it.&#x20;

It helps us avoid falling into the [Singleton pattern](https://gameprogrammingpatterns.com/singleton.html), and does something similar to the [Service Locator pattern](https://gameprogrammingpatterns.com/service-locator.html). Also good for performance reasons, It can handle over a million calls every frame with no issues.

## Using the SystemLocator

To register a new system you can call the <mark style="color:purple;">**SystemLocator**</mark>**.**<mark style="color:green;">**Register**</mark>**(**<mark style="color:blue;">**this**</mark>**)** method, it'll add that system into a dictionary of systems, preventing two of the same system from existing.&#x20;

Then you can get this system from somewhere else using <mark style="color:purple;">**SystemLocator**</mark>**.**<mark style="color:green;">**Get**</mark>**<**<mark style="color:purple;">**T**</mark>**>()**

## <mark style="color:yellow;">**⚠️**</mark>** **<mark style="color:red;">**IMPORTANT!**</mark>&#x20;

Note that is done automatically by classes inheriting <mark style="color:purple;">**System**</mark> and <mark style="color:purple;">**NetworkedSystem**</mark>. They register on <mark style="color:green;">**Awake**</mark>:

<pre><code><strong>public class System : Actor
</strong>    {
        protected override void OnAwake()
        {
            base.OnAwake();
            SystemLocator.Register(this);
        }
    }
</code></pre>

## Examples

<details>

<summary>Getting the spawned players list</summary>

<mark style="color:purple;">EntitySpawnSystem</mark> entitySpawnSystem = <mark style="color:purple;">SystemLocator</mark>.<mark style="color:green;">Get</mark><<mark style="color:purple;">EntitySpawnSystem</mark>>();&#x20;

<mark style="color:purple;">List</mark><<mark style="color:purple;">PlayerControllable</mark>> playersToAssign = entitySpawnSystem.<mark style="color:blue;">SpawnedPlayers</mark>;

</details>

<details>

<summary>Ending the round after detonating a nuke</summary>

_<mark style="color:blue;">// Ends the round, regardless of how many objectives were completed</mark>_ <mark style="color:purple;">SystemLocator</mark>.<mark style="color:green;">Get</mark><<mark style="color:purple;">GamemodeSystem</mark>>().<mark style="color:green;">EndRound</mark>();

</details>
