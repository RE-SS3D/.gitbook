---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Using Asset Data

To use an existing asset database, simply look for its file by <mark style="color:orange;">**`"Assets/Scripts/SS3D/Data/Generated"`**</mark>, find the database you want to use and then call the item you want to grab.

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption><p>Example on what it looks like to find the database.</p></figcaption></figure>

## Examples

{% hint style="warning" %}
Some of these examples have implicit operators to cast them into the correct type.
{% endhint %}

#### Setting an icon for an interaction:

```csharp
// The Icon field is a Sprite field.
// The InteractionIcons.Open is not a Sprite, it is an AssetDatabase.
// There are implicit operators to cast this AssetDatabase into a Sprite.
public override Sprite GetIcon(InteractionEvent interactionEvent)
{
    return Icon != null ? Icon : InteractionIcons.Open;
}
```

#### Setting up tests:

```csharp
// Get local player position, 
// interaction controller and put bikehorn in first hand available.

// Note that we are adding a PDA manually for the test.
AttachedContainer hand = 
    TestHelpers.LocalPlayerSpawnItemInFirstHandAvailable(Items.PDA);
```

#### Creating a world space loading bar

```csharp
// Calling the New() method simply creates an instance for that object.
_loadingBarInstance = WorldSpaceUI.LoadingBar.New();
```
