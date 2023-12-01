# Brace Style

All braces get their own line as it is a C# convention:

**BAD:**

```
class MyClass {
    void DoSomething() {
        if (someTest) {
          // ...
        } else {
          // ...
        }
    }
}
```

**GOOD:**

```
class MyClass
{
    void DoSomething()
    {
        if (someTest)
        {
          // ...
        }
        else
        {
          // ...
        }
    }
}
```

Conditional statements are preferred to be enclosed with braces, irrespective of the number of lines required. Some cases can be pardoned.

**BAD:**

```
if (someTest)
    doSomething();  

if (someTest) doSomethingElse();
```

**GOOD:**

```
if (someTest) 
{
    DoSomething();
}  

if (someTest)
{
    DoSomethingElse();
}
```
