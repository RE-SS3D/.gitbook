---
description: >-
  For the purpose of debugging (maybe even playing some day), this page explain
  how you can join as a client in a SS3D server, in or outside the Unity editor.
---

# Joining a server

{% hint style="warning" %}
We don't have the **SS3D Hub** _yet_, so this is only valid before we have that.
{% endhint %}

## Using the .bat file

First, launch a server by following instructions on the page **Hosting a server**.

Assuming you built the game and have a SS3D.exe file in the Builds folder, you can simply double left click on the <mark style="color:purple;">**`Start SS3D Client - GhostOfBeep.bat`**</mark> to launch a client, with GhostOfBeep as a username.&#x20;

## Using the Command Line Args

{% hint style="danger" %}
This is only applicable for <mark style="color:yellow;">**Built Executables**</mark>.
{% endhint %}

Open a command prompt in your project's path to the <mark style="color:purple;">**`Builds/Config`**</mark>, and run the following command changing the fields appropriately.

```
start SS3D.exe -ip=serverAddress -ckey=clientUserName -skipintro
```

This will launch the client, replace <mark style="color:purple;">**`clientUsername`**</mark> with your username and replace <mark style="color:purple;">**`serverAddress`**</mark> with the desired server address, you can use <mark style="color:purple;">**`localhost`**</mark> or <mark style="color:purple;">**`127.0.0.1`**</mark> for a local server.

## Using Application Settings window

{% hint style="danger" %}
This is only applicable when using the <mark style="color:yellow;">**Unity Engine to join a server**</mark>, which <mark style="color:yellow;">**should be avoided if you're**</mark> <mark style="color:yellow;">**not developing**</mark>.
{% endhint %}

You can set the <mark style="color:purple;">**`Network Type`**</mark> to <mark style="color:purple;">**`Client`**</mark>, the <mark style="color:purple;">**`Editor Server Address`**</mark> to the desired<mark style="color:purple;">**`server IP`**</mark>, or your <mark style="color:purple;">**`local IP (127.0.0.1)`**</mark> if hosting from the same machine, and the <mark style="color:purple;">**`Ckey`**</mark> to your desired <mark style="color:purple;">**`Ckey`**</mark>.

{% hint style="info" %}
You can hover the parameters in Application Settings to get a description on what it does and how to use it.
{% endhint %}
