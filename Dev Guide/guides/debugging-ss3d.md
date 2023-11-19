---
description: >-
  This page aim to show some practices that could be helpful to help you debug
  SS3D.
---

# Debugging SS3D

## Always check your code on host and on client

SS3D is a networked game, some of the code is running server side and some client side. Every time you add or remove something, you should check that it works well both on the host and on the clients.&#x20;

Ideally, you should make tests including one host and multiple clients, at least one, but be careful, some bugs involve two clients and it would appear as working between host and client alone. Hence, try to test with two clients and one host, whenever it's possible and relevant.

Refer to the [Running ](https://ss3d.gitbook.io/programming/guides/running)section to learn how to host and join a server.

##

## Making attributes of class public

In Unity, whenever an attribute is public, it will appear in the gameObject inspector. This allows you to modify attributes during runtime in the gameObject Inspector.

In the below picture, I can modify the Inventory displayed by the inventory UI script, simply by clicking on it, and replacing the reference with the one of my choice.&#x20;

This could be useful to quickly go through all inventories during the run, without having to code a special tool for it.



<img src="../.gitbook/assets/image (3).png" alt="" data-size="original">

Making attributes public is also interesting to observe attribute changes during run time without using an actual debugger or the console. It has the advantage of not disturbing the flow of the game, and not overflowing the debug console.



## Making use of the Input.GetKeyDown() function

Sometimes, what you need to debug involves critical timing, and running some logic. A classic debugger is not good enough or at best makes things really tedious.

To control when you want to get some debugging info, or run some code at the right time, what you could use is the Input.GetKeyDown() function.

This function simply returns true whenever the key of your choice is pushed. Put that in the Update loop of a monoBehaviour and you can log anything you want when you push a key, or run some logic.

```csharp
    public void Update()
    {
        if (Input.GetKeyDown(KeyCode.space))
        {
            // Run some Debug.Log() or some logic
        }
    }
```

Here's an exemple, this little snippet of code allows me to modify a given container by one of my choosing, during run time, when I choose to. It's a simple trick but it's easy to forget about it.&#x20;

```csharp
    public void Update()
    {
        if (Input.GetKeyDown(KeyCode.L))
        {
            Debug.Log("updating left container");

            var container = FindObjectsOfType<AttachedContainer>()
                .Where(x => x.gameObject.name == "leftcontainer").First();
            UpdateContainer(container);
        }
    }
```

## What's destroying my game object ?

SS3D is full of calls to the Destroy() method on game objects and as the game grows finding what's destroying a given game object will become increasingly difficult.

A simple search in your code editor, using Ctrl+f and searching through the whole solution for "Destroy(" can be enough, but it's tedious.&#x20;

Here is an useful trick to find what's destorying your game object. Just add this code on any component on the game object that is destroyed. It will print in the Unity Debug console the stack of methods responsible for the call of OnDisable, and this usually allows to to trace back what's destroying your game object.

```csharp
    void OnDisable()
    {
        // If object will destroy in the end of current frame...
        if (gameObject.activeInHierarchy)
        {
            Debug.LogError("Log an error with a stack trace in debug mode");
        }
    }
```
