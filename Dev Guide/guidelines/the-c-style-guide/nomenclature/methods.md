# Methods

Methods are written in **PascalCase**. For example <mark style="color:green;">`DoSomething`</mark>`()`.

<details>

<summary>Methods that are used as the <mark style="color:blue;">OnChange</mark> callback of a [<mark style="color:purple;">SyncVar</mark>]</summary>

Should have the **`Sync`** prefix, as in:

```
[SyncVar(OnChange = nameof(SyncUsername))] string _username;
```

```
private void SyncUsername(string oldUsername, string newUsername, bool asServer) {}
```

</details>

<details>

<summary>Methods that listen to an <mark style="color:blue;">event</mark></summary>

Should have the prefix Handle, as in:

```
clownBomb.OnExploded += HandleClownBombExploded;
```

```
private void HandleClownBombExploded() 
{
    Honk();
}
```

</details>

<details>

<summary>Methods that are preceded by the [<mark style="color:purple;">Server</mark>] attribute</summary>

Do not need to have the `Server` prefix on them. This is still something we are thinking about, both uses are fine for now.

As in:

```
[Server]
public void ServerKillPlayer() {}
[Server]
public void KillPlayer() {}
```

</details>

<details>

<summary>Methods that are preceded by the [<mark style="color:purple;">ServerRpc</mark>] attribute</summary>

Need to have the `Cmd` prefix on them, as in:

```
[ServerRpc]
public void CmdSpawnItem(GameItems item) 
{
    SpawnItem(item);
}
```

</details>

<details>

<summary>Methods that are preceded by the [<mark style="color:purple;">ObserversRpc</mark>] attribute</summary>

Need to have the `Rpc` prefix on them, as in:

```
[ObserversRpc]
private void RpcSpawnVisualProjectives() 
{
   _particleSystem.Play();   
}
```

</details>
