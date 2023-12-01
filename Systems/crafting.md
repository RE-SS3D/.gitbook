# 🛠 Crafting

See the [Broken link](broken-reference "mention") design doc first for more info on the design of the system.



### Crafting System

The crafting system script handle storing all possible recipe.

Recipes are organised in an efficient manner that allow to search very fast through them, given we know the target of the recipe and the name of the interaction to execute it.

It's using the following structure :

```
Dictionary<ItemId, Dictionary<string, CraftingRecipe>>
```

The system starts by looking for all recipes in the recipe asset database and fill the structure.

Both client and server have access to the full recipe list.

### Crafting interaction

The other major element of the system is the crafting interaction abstract class. When you want to add a new interaction, inherit from it, as it will provide the basis for what you need, if you want to implement a new interaction that will result in crafting something.

You can use the `SliceInteraction.cs`  script as an implementation example. Notice how the code override the CanCraft method, so it can add its own conditions to allow this specific crafting.

For a crafting interaction to work in game, the interaction needs to be put on an item that will act as the source of that interaction.&#x20;

In the case of the slice interaction, we could add it to a knife, or any other slicy item. For that, we create a new script that inherits from IInteractionSource :&#x20;

```
 public class Slice : MonoBehaviour, IInteractionSourceExtension
    {
        public void GetSourceInteractions(IInteractionTarget[] targets, List<InteractionEntry> interactions)
        {
            SliceInteraction interaction = new SliceInteraction(2f, GetComponent<InteractionSource>().transform);

            foreach (IInteractionTarget target in targets)
            {
                interactions.Add(new InteractionEntry(target, interaction));
            }
        }
    }
```

Just put that script on your knife game object and you're good to go. See how it creates a new sliceInteraction.

### Adding recipes

Recipes are simple scriptable objects in Assets/Content/Data/Recipes currently. Easy to set up.

Creating a new recipe is very simple : \


<figure><img src=".gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

You can then fill up the recipe with everything it needs. Should be explicit enough.

<figure><img src=".gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

If you want your recipe to be accessible in game though, you'll need to [add it to the recipe asset database](asset-data/).

