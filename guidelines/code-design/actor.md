# Actor

<mark style="color:purple;">**Actor**</mark> is our substitute for <mark style="color:purple;">**MonoBehaviours**</mark>, it optimizes and creates shortcuts for useful stuff.

<details>

<summary>Moving an object</summary>

Moving object with MonoBehaviours

```
transform.position = new Vector3(0, 0, 123);
```

Moving an object with Actor

```
Position = new Vector3(0, 0, 123);
```

The reason we do that is because <mark style="color:blue;">transform</mark>**.**<mark style="color:blue;">position</mark> **goes into C++** every single time to get the transform, which can lead to performance issues later in development. Also it is a nice shortcut.

You can use the same idea for <mark style="color:blue;">Rotation</mark>, and for getting the directions relative to that transform, like <mark style="color:blue;">Forward,</mark> <mark style="color:blue;">Up</mark>, <mark style="color:blue;">Down</mark>.

</details>

<details>

<summary>Callbacks</summary>

The standard callback methods also have been changed, you'll use <mark style="color:green;">**OnStart**</mark> instead of Start, <mark style="color:green;">**OnAwake**</mark> instead of <mark style="color:green;">**Awake**</mark>, <mark style="color:green;">**OnDestroyed**</mark> instead of <mark style="color:green;">**OnDestroy**</mark>.

Another think you need to know is <mark style="color:green;">**HandleUpdate**</mark>, <mark style="color:green;">**HandleLateUpdate**</mark> and <mark style="color:green;">**HandlePreUpdate**</mark>. All these methods have one thing in common: they listen to an [<mark style="color:blue;">**event bus**</mark>](broken-reference) to be called.

The reason being that in standard Unity environment, the engine searches through the entire instantiated object's list and tries to find the <mark style="color:green;">**Update**</mark> method declared somewhere. That's very slow.

Instead, our friend from the [CS Framework](https://github.com/coimbrastudios/framework) decided to create an [<mark style="color:blue;">**event bus**</mark>](broken-reference) for the **player loop timing**, so Unity only needs to worry about one object with the <mark style="color:green;">**Update**</mark> method.

Every method that listens to the <mark style="color:purple;">**UpdateEvent**</mark> [<mark style="color:blue;">**event bus**</mark>](broken-reference) and its variants will then be called.

</details>

## Networking

For networked objects, instead of <mark style="color:purple;">**NetworkBehaviour**</mark>, you will use <mark style="color:purple;">**NetworkActor**</mark>. They work the same way as <mark style="color:purple;">**Actor**</mark>.
