# Action

An <mark style="color:purple;">**Action**</mark> is an <mark style="color:blue;">**event**</mark> that depends on an <mark style="color:blue;">**object**</mark> to exist.&#x20;

The <mark style="color:purple;">**Action**</mark>** **<mark style="color:blue;">**event**</mark> should be used when we don't need something to be accessed globally, like a button being pressed, or when we need to listen from something from a specific object.

<details>

<summary>Declaring</summary>

<mark style="color:purple;">**Actions**</mark> have to be declared as the first thing inside a <mark style="color:blue;">**object**</mark> with the <mark style="color:blue;">**event**</mark> keyword.

```
public class ButtonView : Actor 
{
    public event Action OnButtonPressed;
}
```

Only the <mark style="color:blue;">**object**</mark> that declares the <mark style="color:blue;">**event**</mark> can invoke it.

It is noted that you can use an <mark style="color:purple;">**Action**</mark> to send data too:

```
public event Action<int> OnNumberUpdated;
public event Action<Item> OnItemUpdated;
```

</details>

## Using an <mark style="color:purple;">Action</mark>

Let's imagine you have a granade in your character's hand. Pretty common sight in a Low RP server. In the code, usually we would have something like:

```
public class Granade : Explosive 
{
    public event Action OnPinRemoved;
    
    public void RemovePin() 
    {
        // Do pin removal logic.
    
        OnPinRemoved?.Invoke();
    }
}
```

The <mark style="color:purple;">**OnPinRemoved**</mark> <mark style="color:blue;">**event**</mark> will be used to to tell listeners that subscribed to that granade's event that the granade's pin was removed. The relevance of that <mark style="color:purple;">**OnPinRemoved**</mark> <mark style="color:blue;">**event**</mark> is usually for UI related purposes, or running a local animation of a granade pin flying through your screen.&#x20;

Something like:

```
public class GranadePinAnimationView : Actor 
{
    private GranadePinAnimation _granadePinAnimation;

    private Granade _granade;
    
    protected override OnAwake() 
    {
        _granade.OnPinRemoved += HandlePinRemoved;
    }
    
    protected override OnDestroyed() 
    {
        _granade.OnPinRemoved -= HandlePinRemoved;
    }
    
    private void HandlePinRemoved() 
    {
        _granadePinAnimation.RunAnimation();
    }
}
```

You might even think it would be easier to call it directly, and depending on your logic it might be, but we are assuming that in this case its better to keep the classes decoupled.
