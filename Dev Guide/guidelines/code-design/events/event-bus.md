# Event Bus

The <mark style="color:blue;">**event bus**</mark> is a design pattern, it serves the purpose of a "global event system" as it can be invoked from anyone, anywhere and can be listened by anyone, anywhere.&#x20;

The implementation we use was created by the [CS Framework](https://github.com/coimbrastudios/framework) and we use it to create new event buses. To understand further on the design pattern itself, you can [read this article](https://www.techyourchance.com/event-bus/).

We use these <mark style="color:blue;">**events**</mark> when we want something that will be used in more than one place, without having to care about <mark style="color:blue;">**object**</mark> relation.&#x20;

We usually want <mark style="color:blue;">**events**</mark> to be fired by <mark style="color:blue;">**systems**</mark> when we want to inform other objects something has happened, like a round timer being updated, a player that spawned, an object that was picked up.

<details>

<summary>Creating</summary>

To create a new <mark style="color:blue;">**event**</mark>, we use <mark style="color:blue;">**partial structs**</mark> that inherit from the <mark style="color:purple;">**IEvent**</mark>** **<mark style="color:blue;">**interface**</mark>. The reason for the <mark style="color:blue;">**partial**</mark> keyword is that the [CS Framework](https://github.com/coimbrastudios/framework) uses the [Roslyn code generation tools](https://github.com/dotnet/roslyn) to create the rest of the necessary logic on that <mark style="color:blue;">**struct**</mark>.

```csharp
public partial struct RoundTimerUpdatedEvent : IEvent 
{
    public int TimerSeconds;
}
```

It is also interesting and kind-of but not obligatory standard to create constructors for these <mark style="color:blue;">**events**</mark>, they can become quite large lines at times.

```csharp
public partial struct RoundTimerUpdatedEvent : IEvent 
{
    public int TimerSeconds;
    
    public RoundTimerUpdatedEvent(int timerSeconds) 
    {
        TimerSeconds = timerSeconds;
    }
}
```

</details>

Pretty straight-forward isn't it? Well, now for the usage.

<details>

<summary>Invoking</summary>

Invoking is the easiest part. You just need to know what you want to invoke and when. The code below creates a new instance of our <mark style="color:blue;">**event**</mark>, using the constructor we just defined and then invokes it. We also have to specify who called that <mark style="color:blue;">**event**</mark>, in our case we use the this keyword to say that the <mark style="color:blue;">**class's**</mark> instance that called it.

All event invoking should happen after <mark style="color:green;">**OnAwake**</mark>.

```csharp
RoundTimerUpdatedEvent event = new RoundTimerUpdatedEvent(30);
event.Invoke(this);
```

</details>

<details>

<summary>Listening</summary>

Listening is the most complex of them, because it contains scary words and more complex management.

It is advised that you add event listeners on <mark style="color:green;">**OnAwake**</mark>, to avoid initialization issues.

<pre class="language-csharp"><code class="lang-csharp"><strong>protected override void OnAwake() 
</strong>{
<strong>    base.OnAwake();
</strong>    
    RoundTimerUpdated.AddListener(HandleRoundTimerUpdated);
}
</code></pre>

<mark style="color:blue;">**base**</mark>**.**<mark style="color:green;">**Awake**</mark>**()** calls the parent class's <mark style="color:green;">**Awake**</mark> function. Then we add the method that will be called when the <mark style="color:blue;">**event**</mark> is invoked. We'll declare the method as follows:

```csharp
private void HandleRoundStateUpdated(ref EventContext ctx, in RoundStateUpdated e) 
{
    Debug.Log(e.TimerSeconds);
}
```

The <mark style="color:purple;">**EventContext**</mark> is usually unused but it gives us information about the invoking itself. Then we have the <mark style="color:blue;">**event**</mark> we created, it is the <mark style="color:blue;">**struct**</mark> that we previously created.&#x20;

The <mark style="color:blue;">**ref**</mark> and <mark style="color:blue;">**in keywords**</mark> are there for optimization reasons but they are required, so always add them if your **IDE** doesn't autocomplete correctly.

One thing to note here is that you have to remove the listeners eventually, you have to do it on the <mark style="color:green;">**OnDestroyed**</mark> callback, but if you're using any class that inherits from <mark style="color:purple;">**Actor**</mark> or <mark style="color:purple;">**NetworkActor**</mark>, it already unsubscribes from it if you use the <mark style="color:green;">**AddHandle**</mark> method when listening to the events.

```csharp
protected override void OnAwake() 
{
    base.OnAwake();
    
    AddHandle(RoundTimerUpdated.AddListener(HandleRoundTimerUpdated));
}
```



</details>

<details>

<summary>Examples</summary>

One thing we have to keep in mind is that, with networking, we have to use a **data-driven design**, as we cannot depend on one-time of <mark style="color:blue;">**events**</mark> only, a user has to be able to disconnect and reconnect back later with no issues, if we did not use **data-driven**, the user would lose that information.

So, we can have the best of both worlds, [<mark style="color:purple;">**FishNet**</mark> ](../../../networking/fishnet-networking/)already has callbacks when <mark style="color:purple;">**SyncVars**</mark> are changed, and they are changed to the correct value when the user enters the server.

In the <mark style="color:purple;">**ReadyPlayersSystem**</mark>, we have:

```csharp
[SyncObject] private readonly SyncList<string> _readyPlayers = new();
```

This is a <mark style="color:purple;">**SyncList**</mark>, it updates automatically for all clients, and it as a <mark style="color:blue;">**OnChange**</mark> callback. It makes us able to do this:

```csharp
_readyPlayers.OnChange += HandleReadyPlayersChanged;
```

When the list is changed, we call the <mark style="color:green;">**HandleReadyPlayersChanged**</mark> method.

```csharp
private void HandleReadyPlayersChanged(SyncListOperation op, int index, string s, string newItem1, bool asServer)
{
    SyncReadyPlayers();
}
```

The method then calls the <mark style="color:green;">**SyncReadyPlayersMethod**</mark>, calling, then, our <mark style="color:blue;">**event**</mark>.

```csharp
private void SyncReadyPlayers()
{
    ReadyPlayersChanged readyPlayersChanged = new(_readyPlayers.ToList());
    readyPlayersChanged.Invoke(this);
}
```

All this trajectory is to ensure our client doesn't lose anything when he rejoins a game and can load stuff back correctly, not to mention this is way easier than doing **RPCs** all over the code.

Anything in the codebase can listen to that event, in that case we use for updating the UI, that changes the player name's color if they are ready or not.

</details>
