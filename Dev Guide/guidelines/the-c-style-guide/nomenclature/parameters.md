# Parameters

Parameters are written in **camelCase**.

**BAD:**

```
void DoSomething(Vector3 Location)
```

**GOOD:**

```
void DoSomething(Vector3 location)
```

Single character values are to be avoided except for temporary looping variables. You can also use **`_`** for unused variables, **`m`** for [<mark style="color:blue;">**network messages**</mark>](../../../networking/fishnet-networking/network-message.md) and **`e`** for [<mark style="color:blue;">**event bus's events**</mark>](../../code-design/events/event-bus.md).
