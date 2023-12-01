# Spacing

Spacing is especially important to make code more readable.

#### Indentation

Indentation should be done using **tabs** — never **spaces** .

**Blocks**

Indentation for blocks uses **tabs** for optimal readability:

**BAD:**

```
for (int i = 0; i < 10; i++) 
{
  Debug.Log("index=" + i);
}
```

**GOOD:**

```
for (int i = 0; i < 10; i++) 
{
    Debug.Log("index=" + i);
}
```

**Line Wraps**

Indentation **tab** for line wraps should use **4 spaces** (not the default 8):

**BAD:**

```
CoolUiWidget widget =
        someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

**GOOD:**

```
CoolUiWidget widget =
    someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

#### Line Length

Lines should be no longer than **100** characters long.

#### Vertical Spacing

There should be just one or two blank lines between methods to aid in visual clarity and organization. Whitespace within methods should separate functionality, but having too many sections in a method often means you should refactor into several methods.
