---
description: >-
  For the purpose of debugging (maybe even playing some day), this page explain
  how you can host a SS3D server, in or outside the Unity editor.
---

# Hosting a server

{% hint style="warning" %}
We don't have the **SS3D Hub** _yet_, so this is only valid before we have that.
{% endhint %}

The process of hosting a server, where you can play and have players connected to your server is possible via two paths:

## Pre-launch instructions

###

### Using the .bat file

Assuming you built the game and have a SS3D.exe file in the Builds folder, you can simply double left click on the <mark style="color:purple;">**`Start SS3D Host.bat`**</mark> to launch a server, with john as a username.&#x20;

### Using the Command Line Args

{% hint style="danger" %}
This is only applicable for <mark style="color:yellow;">**Built Executables**</mark>.
{% endhint %}

To host a server **outside** the **Unity Editor**, first you have to build SS3D in the **`Builds`** folder of your SS3D project. You can then open a command prompt, move to the `Builds` folder and type :

```
start SS3D.exe -host -ckey=hostUsername -skipintro
```

Replace <mark style="color:purple;">**`hostUsername`**</mark> by whatever username you want to use. Don't hit enter yet and skip to launch instructions.

### Using Application Settings window

{% hint style="danger" %}
This is only applicable when using the <mark style="color:yellow;">**Unity Engine for hosting**</mark>, which <mark style="color:yellow;">**should be avoided if you're**</mark> <mark style="color:yellow;">**not developing**</mark>.
{% endhint %}

You can set the <mark style="color:purple;">**`Network Type`**</mark> to <mark style="color:purple;">**`Host`**</mark>, the <mark style="color:purple;">**`Editor Server Address`**</mark> to your <mark style="color:purple;">**`server IP`**</mark>, or your <mark style="color:purple;">**`local IP (127.0.0.1)`**</mark> if hosting from the same machine, and the <mark style="color:purple;">**`Ckey`**</mark> to your desired <mark style="color:purple;">**`Ckey`**</mark>.

{% hint style="info" %}
You can hover the parameters in Application Settings to get a description on what it does and how to use it.
{% endhint %}

## Launch Instructions

{% hint style="info" %}
This is valid for <mark style="color:yellow;">**Unity Editor**</mark> and <mark style="color:yellow;">**Built Executable**</mark> usage.
{% endhint %}

In the <mark style="color:purple;">**`permissions.txt`**</mark> file, inside the <mark style="color:purple;">**`Builds/Config`**</mark> folder. The username should have <mark style="color:purple;">**`Administrator`**</mark> written on the same line in the <mark style="color:purple;">**`permissions.txt`**</mark> file, otherwise it will not able to host the server. _This should probably be automated eventually._

You can now hit enter or hit play depending on your case. **The server will be launched and you can join with a client now.**

Once started, go to server settings and click on <mark style="color:purple;">**`start round`**</mark> like in the picture below.

<img src="https://user-images.githubusercontent.com/14344825/210403775-67a1bc1a-1651-4e9a-b4f9-937f0014d85d.png" alt="" data-size="original">

## Troubleshooting

<details>

<summary>Nothing appearing on the server page when hosting</summary>

Check the host username in the command:

```
start SS3D.exe -host -ckey=hostUsername -skipintro
```

It must **exactly** correspond to whatever username is present in the <mark style="color:purple;">**`permissions.txt`**</mark> file, in the <mark style="color:purple;">**`Builds/Config`**</mark> folder.

</details>
