# Switch Statements

Switch-statements come with `default` case by default (heh). If the `default` case is never reached, be sure to remove it.

If the `default` case is an unexpected value, it is encouraged to log and return an error

**BAD**

```
switch (variable) 
{
    case 1:
        break;
    case 2:
        break;
    default:
        break;
}
```

**GOOD**

```
switch (variable) 
{
    case 1:
        break;
    case 2:
        break;
}
```

**BETTER**

```
switch (variable) 
{
    case 1:
        break;
    case 2:
        break;
    default:
        Debug.LogError("Unexpected value when...");
        return;
}
```
