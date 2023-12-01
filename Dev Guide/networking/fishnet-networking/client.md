# Client

## Client

The client is a game instance that is connected to a server game instance, it receives all network packets the server wants to send it, so a character position is set by the server so every client sees your player in the same position.

## Code that runs on the client

Logic that will only run on the client game instance. Usually in Unity game development we use attributes for defining those rules, they are little tags that go above the method declaration, which does depend a lot on the networking framework you’re using in your game.

We are using **FishNet Networking**, the attribute is **\[**<mark style="color:purple;">**Client**</mark>**]**, but code that is not sent to either clients or the server is always local to that game instance, so you only use that when you want to prevent the server game instance running that code.

## Client attribute

\[<mark style="color:purple;">Client</mark>]

The client attribute prevents the server from running a method.

## Examples

<details>

<summary>Initializing a game screen</summary>

```
[Client]
private void Setup()
{
    LastScreen = ScreenType.None;

    if (_canvasGroup != null)
    {
        bool foundCanvas = TryGetComponent(out CanvasGroup canvasGroup);
        _canvasGroup = foundCanvas ? canvasGroup : GameObjectCache.AddComponent<CanvasGroup>();
    }

    SetScreenState(ScreenType.Lobby, true);

    ChangeGameScreenEvent.AddListener(HandleChangeGameScreen);
    ChangeCameraEvent.AddListener(HandleChangeCamera);
}
```

The \[<mark style="color:purple;">Client</mark>] attribute is preventing a server from preparing an UI, as it should not exist in a headless server. The server doesn't **play** the game, it **manages** the game.

</details>
