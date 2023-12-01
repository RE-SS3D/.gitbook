# Delegates

Delegates are written in **PascalCase**.

When declaring delegates, DO add the suffix **EventHandler** to names of delegates that are used in events.

**BAD:**

```
public delegate void Click()
```

**GOOD:**

```
public delegate void ClickEventHandler()
```

DO add the suffix **Callback** to names of delegates other than those used as event handlers.

**BAD:**

```
public delegate void Render()
```

**GOOD:**

```
public delegate void RenderCallback()
```

## <mark style="color:yellow;">**⚠️**</mark>** **<mark style="color:red;">**IMPORTANT!**</mark>

**Using built.in C# features, such as Action, is encouraged in place of delegates.**
