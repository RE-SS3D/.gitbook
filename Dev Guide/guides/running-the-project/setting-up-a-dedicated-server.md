---
description: >-
  For the purpose of debugging (maybe even playing some day), this page explain
  how you can open a server-only SS3D server, in or outside the Unity editor.
---

# Setting up a dedicated server

{% hint style="warning" %}
We don't have the **SS3D Hub** _yet_, so this is only valid before we have that.
{% endhint %}

The process of opening SS3D as server only, where you can play and have players connected to your server is possible via two paths:

## Pre-launch instructions

### Using the Command Line Args

{% hint style="danger" %}
This is only applicable for <mark style="color:yellow;">**Built Executables**</mark>.
{% endhint %}

To open a server **outside** the **Unity Editor**, first you have to build SS3D in the **`Builds`** folder of your SS3D project. You can then open a command prompt, move to the `Builds` folder and type :

```
start SS3D.exe -serverOnly
```

### Using Application Settings window

{% hint style="danger" %}
This is only applicable when using the <mark style="color:yellow;">**Unity Engine to open a server**</mark>, which <mark style="color:yellow;">**should be avoided if you're**</mark> <mark style="color:yellow;">**not developing**</mark>.
{% endhint %}

You can set the <mark style="color:purple;">**`Network Type`**</mark> to <mark style="color:purple;">**`Server`**</mark>.

{% hint style="info" %}
You can hover the parameters in Application Settings to get a description on what it does and how to use it.
{% endhint %}
