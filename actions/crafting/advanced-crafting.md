# Advanced Crafting

Advanced Crafting is a way for characters to make better Weapons, Clothing, Food and other various items, using a specific workstation (such as a Workbench, Stove, Microwave, Fabricator, Forge or other).&#x20;

In order to implement Advanced crafting, an Advanced Recipe List (ARL) should be implemented first.

## Advanced Recipe List (ARL)

This list should contain the ID’s and quantities of various items and materials used for crafting, ID’s for needed tools and the ID’s and quantities of the resulting items, as well as the type of the crafting station.&#x20;

Example of the entry from the said list:

```
{
  "type": "workbench",
  "result": "Flamethrower",
  "time": "20 s",
  "tool": [ { "Screwdriver " } ],
  "component": [ [ [ "Welding Tool", 1 ], [“Igniter”, 1], [“Metal_rod”, 1] ] ]
},
```

Where (the names of these can change):&#x20;

* "type" is a type of the crafting station;
* "result" is the object, created in the end of the completed recipe;
* "time" is the length of waiting for an action in the recipe to be completed;
* "tool" is the object, that is supposed to be used (depleting the set amount of fuel or durability for one action), but not consumed;
* "component" is the set of objects consumed in the crafting process;

This set of recipes requires a Screwdriver as a tool, 1 Igniter, 1 Rod and 1 Welding Tool to create Flamethrower

Crafting menu should be implemented for this kind of crafting.&#x20;
