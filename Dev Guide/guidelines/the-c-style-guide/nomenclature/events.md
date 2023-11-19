# Events

Prefix <mark style="color:blue;">**event**</mark> methods with the prefix **On**.

**BAD:**

```
public static event CloseCallback Close;
public event Action Changed;
```

**GOOD:**

```
public static event CloseCallback OnClose;
publc event Action OnChanged;
```
