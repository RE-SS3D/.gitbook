---
description: >-
  Class used to get game subsystems, using generics and then making cache of said
  subsystems.
---

# SubSystems

The <mark style="color:purple;">**SubSystems**</mark> class is used to easily find any subsystem that has been registered on it.&#x20;

It helps us avoid falling into the [Singleton pattern](https://gameprogrammingpatterns.com/singleton.html), and does something similar to the [Service Locator pattern](https://gameprogrammingpatterns.com/service-locator.html). Also good for performance reasons, It can handle over a million calls every frame with no issues.

## Using the SubSystems class

To register a new subsystem you can call the <mark style="color:purple;">**SubSystems**</mark>**.**<mark style="color:green;">**Register**</mark>**(**<mark style="color:blue;">**this**</mark>**)** method, passing in a class that extends from <mark style="color:purple;">**SubSystem**</mark> or <mark style="color:purple;">**NetworkSubSystem**</mark>, it'll add that subsystem into a dictionary of subsystems, preventing two of the same subsystem from existing.&#x20;

Then you can get this subsystem from somewhere else using <mark style="color:purple;">**SubSystems**</mark>**.**<mark style="color:green;">**Get**</mark>**<**<mark style="color:purple;">**T**</mark>**>()**

## <mark style="color:yellow;">**⚠️**</mark>** **<mark style="color:red;">**IMPORTANT!**</mark>&#x20;

Note that is done automatically by classes inheriting <mark style="color:purple;">**SubSystem**</mark> and <mark style="color:purple;">**NetworkedSubSystem**</mark>. They both register on <mark style="color:green;">**Awake**</mark> and unregister on <mark style="color:green;">**Destroy**</mark>:

<pre><code><strong>public class SubSystem : Actor
</strong>    {
        protected override void OnAwake()
        {
            base.OnAwake();
            SubSystemLocator.Register(this);
        }

        protected override void OnDestroyed()
        {
            base.OnDestroyed();
            SubSystemLocator.Unregister(this);
        }
    }
</code></pre>

## Examples

<details>

<summary>Getting the spawned players list</summary>

<mark style="color:purple;">EntitySpawnSubSystem</mark> entitySpawnSubSystem = <mark style="color:purple;">SubSystems</mark>.<mark style="color:green;">Get</mark><<mark style="color:purple;">EntitySpawnSubSystem</mark>>();&#x20;

<mark style="color:purple;">List</mark><<mark style="color:purple;">PlayerControllable</mark>> playersToAssign = entitySpawnSubSystem.<mark style="color:blue;">SpawnedPlayers</mark>;

</details>

<details>

<summary>Ending the round after detonating a nuke</summary>

_<mark style="color:blue;">// Ends the round, regardless of how many objectives were completed</mark>_ <mark style="color:purple;">SubSystems</mark>.<mark style="color:green;">Get</mark><<mark style="color:purple;">GamemodeSubSystem</mark>>().<mark style="color:green;">EndRound</mark>();

</details>
