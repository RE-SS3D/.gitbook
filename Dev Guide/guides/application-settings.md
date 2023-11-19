# Application Settings

{% hint style="danger" %}
<mark style="color:yellow;">**All**</mark> the parameters in that window are <mark style="color:yellow;">**overridden**</mark> in built executables. They are then defined by the [**Command Line Args**](application-settings.md#command-line-args).
{% endhint %}

## Command Line Args

The command line args are various symbols used to define arguments to be used by the SS3D application when it runs. The reason for it existing is to easily add Hub support for it when we eventually have it.

Here's a little example on how they look, you can find all them in the <mark style="color:purple;">**`CommandLineArgs.cs`**</mark> file

<details>

<summary>Snippet of what are the args in <mark style="color:purple;"><strong><code>CommandLineArgs.cs</code></strong></mark></summary>

```
/// <summary>
/// The "-serveronly" arg in the executable.
/// </summary>
public const string ServerOnly = "-serveronly";
/// <summary>
/// The "-host" arg in the executable.
/// </summary>
public const string Host = "-host";
/// <summary>
/// String.
/// </summary>
public const string Ip = "-ip=";
/// <summary>
/// String.
/// This is temporary, in production use, this will not exist,
/// and be replaced by the token, and then the server will get the Username.
/// </summary>
public const string Ckey = "-ckey=";
/// <summary>
/// String.
/// in production this will be sent by the Hub to the client executable.
/// </summary>
public const string AccessToken = "-token=";
/// <summary>
/// Bool.
/// Skips the intro.
/// </summary>
public const string SkipIntro = "-skipintro";
/// <summary>
/// Bool.
/// Disables the discord integration.
/// </summary>
public const string EnableDiscordIntegration = "-enablediscordintegration";
```

</details>

## Using Application Settings window

{% hint style="danger" %}
This is only applicable when using the <mark style="color:yellow;">**Unity Engine**</mark>, which <mark style="color:yellow;">**should be avoided if you're**</mark> <mark style="color:yellow;">**not developing**</mark>.
{% endhint %}

The application settings window reflects information used on the **Command Line Args**, it is useful for Editor overrides and internally we use it along the command line args when using built executables.

In the project settings window, you can find the **Application Settings** group, where you can see all the settings related to what configurations the game will use when running.&#x20;

This only contains settings related to the application use. Graphics, sound, and user settings will not be defined there.

<details>

<summary>Finding the Application Settings window</summary>

Open the <mark style="color:purple;">**Project Settings**</mark> window in the **Unity Editor** and look for the <mark style="color:purple;">**SS3D**</mark> group and inside it you'll find <mark style="color:purple;">**Application Settings**</mark>.

<img src="../.gitbook/assets/image (2).png" alt="" data-size="original">

</details>

{% hint style="info" %}
You can hover the parameters in Application Settings to get a description on what it does and how to use it.
{% endhint %}
