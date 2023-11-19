# Server

## What is a Server?

The server is an instance of the game that does all the network management, sending network packets (small portions of data) to client game instances that are connected to that server.&#x20;

What will be sent to clients and what will remain on the server is on the programmer to decide, that’s what network programming is.

It guarantees every client game instance is seeing the game game, otherwise it would be analogue as seeing two different games being played in two different PCs.

## Code that runs on the server

Logic that will only run on the server game instance, so any information not networked from any clients are unknown to the server, we cannot just network everything, that's a lot of information to send over the network, we are here to manage what should be networked and what should not.

All the code run in the server, will only run on the server. If we were to set a variable on the server and not replicate that logic on the client, that means the client would never know that was changed.

## Server Attribute

**\[**<mark style="color:purple;">**Server**</mark>**]**

The Server attribute is used when we want to run methods only in the server.&#x20;

## Examples

<details>

<summary>Setting a variable</summary>

<pre><code><strong>/// &#x3C;summary>
</strong><strong>/// Sets a new controlling soul.
</strong><strong>/// &#x3C;/summary>
</strong><strong>[Server]
</strong>public void SetControllingSoul(Soul soul)
{
        _controllingSoul = soul;

        if (soul == null)
        {
        RemoveOwnership();
        }
        else
        {
        GiveOwnership(soul.Owner);
        }
}
</code></pre>

With the example code, you can see the **\[**<mark style="color:purple;">**Server**</mark>**]** attribute, it always comes in the line above the method and has to be after the XML documentation of that method.&#x20;

The server attribute, prevents anything that isn't the server to run that method.

This is done to prevent clients from setting who is controlling a player _x_, its a way to prevent exploiting.&#x20;

</details>

<details>

<summary>Initializing the gamemode</summary>

```csharp
[Server]
private void InitializeGamemode()
{
            // Creates an instance of the SO, to avoid using the file.
            _gamemode = Instantiate(_gamemode);

            _gamemode.OnInitialized += HandleGamemodeInitialized;
            _gamemode.OnFinished += HandleGamemodeFinalized;
            _gamemode.OnObjectiveUpdated += HandleObjectiveUpdated;

            _gamemode.InitializeGamemode();
}
```

This code is only run on the server, because it initializes the gamemode, if it ran in every client, we would initialize the gamemode in each client, instead of doing once in the server with trusted data.

</details>
