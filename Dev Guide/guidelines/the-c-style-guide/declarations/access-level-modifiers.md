# Access Level Modifiers

Access level modifiers should be explicitly defined for <mark style="color:blue;">**classes**</mark>, <mark style="color:green;">**methods**</mark> and <mark style="color:blue;">**member variables**</mark>. This includes defining private even though C# will implicitly add it.

Use the least accessible access modifier, except for public member that is expected to be used by other <mark style="color:blue;">**classes**</mark> in the future.

#### Fields & Variables

Prefer single declaration per line.

**BAD:**

```
string username, twitterHandle;
```

**GOOD:**

```
string username;
string twitterHandle;
```
