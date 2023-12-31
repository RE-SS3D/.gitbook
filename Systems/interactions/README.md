---
cover: ../.gitbook/assets/ProbablyNot_Chase.png
coverY: 0
---

# 🖐 Interactions

## Overview <a href="#docs-internal-guid-74bb890e-7fff-0d3e-820c-85826751e629" id="docs-internal-guid-74bb890e-7fff-0d3e-820c-85826751e629"></a>

Interactions are not inheriting from monobehaviour. This means that interactions are not components on an game object. Interactions are generated by an interaction target or interaction source, which both can be on game objects.

### Basic structure

The fundamental parts of the system are the source, the target, and the interaction.

The source is used to perform the interaction. When holding nothing, it is the hands of the player. When an item is held it is the source. Sources are structured like a tree. A source can have a parent and you can traverse up, depending on what information you need. Right now the source structure is a maximum of 2 deep (hands an tools) but that might change.

The target is on what the interaction is performed, essentially what the player clicks. It can be anything from another player to a floor tile. There can be multiple targets per game object.

Interactions are created whenever the player wants to interact. This can happen in both the source and targets. They are essentially the results of interacting and modify the world. These interactions are always run on the server but there are also client interactions to show client only things.
