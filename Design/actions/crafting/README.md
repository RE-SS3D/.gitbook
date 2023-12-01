# 🛠 Crafting

Crafting is a game mechanic of using various items and materials and transforming them into different items. The overall guidelines are:

* Players should be able to craft Makeshift items without accessing menus, just by using interactions of items on other items.
* Players should be able to interact with crafting stations for Advanced crafting, which might require a menu.
* Players should only be able to craft using items that are in their external inventory slots (hands, pockets etc.) or located in the containers, opened by the player.
* Crafting is set to a timer. Upon timer completion the requirements are consumed and the result is created.
* There should be a progress bar to show how much time you have left to craft.
* The timer should depend on the condition of the character's hands (see Medical channel or related design documents).
* The timer variable should be a float value.
* There should be lists of crafting recipes, made in structured data format like JSON or ScriptableObject to store recipes in.
* Crafting recipes should be able to work with traditional items like cable coils and reagents like welding fuel.
* Crafting recipes should be able to work with multiples of one item, such as stackable items (only for results for Makeshift crafting).
* Crafting recipes can require certain tools in order to complete. These tools are not consumed when crafting is complete.
* Multiple kinds of tools can be required by one recipe.
* In case of working with reagents there should be an allowance for a deviation from the recipe. For example, there might be a 'purity' function which allows the crafting process if the reagents and reactants are present within a set tolerance of their required ratio (See Substances channel or related design documents).
* Crafting should contain a 'quality' function that depends on how much the crafting process deviates from the recipe (for example, more the 'purity' of the reagent or cooking time deviates from the ones stated in the recipe, the lower quality should be).
* Quality should affect the stats of the crafting result (lower quality weapons deal less damage, lower quality food contains less nutrients and has a higher chance of giving food poisoning)
* Quality should be able to be depleted during crafting, in which case the result should be replaced with a useless "failure" item (like "Burned mess" for food).
* If the result of a recipe is an item, it should be put in the character's active hand if it is empty.
* If a character's active hand is full, then the result should be put in the character's other hand if it is empty.
* If both hands are full or if the result is not a pickupable item, the result should be placed on the nearest empty tile to the one that the character is currently occupying.
