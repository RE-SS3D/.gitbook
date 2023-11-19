# Fields

<mark style="color:blue;">**Private**</mark> fields have the \_ prefix, <mark style="color:blue;">**static**</mark>, <mark style="color:blue;">**const**</mark> and <mark style="color:blue;">**public**</mark> fields are in **UpperCamelCase**.

For example:

```
public class MyClass 
{
    public int PublicField;
    private int _packagePrivate;
    private int _myPrivate;
    protected int _myProtected;
}
```

**BAD:**

```
private int myPrivateVariable
```

**GOOD:**

```
private int _myPrivateVariable
```

#### Field Position

All fields should be at the top of the class, before any methods.
