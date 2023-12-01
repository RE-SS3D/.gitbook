# Interface

Well, bare in mind that this is the design idea, which we haven't executed yet:

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

## Exit Button

Simply the button to exit the map editor.

## Tools Menu

This menu contains all the tools to edit the tilemap, and has the following tools:

1. Select
   1. Move around with the mouse.
2. Edit
   1. Uses the selected object in the object menu with a place hint of the position.
3. Move (with mouse)
   1. Move an object precisely (only for non-tile-locked objects)
4. Undo
   1. Undo
5. Redo
   1. Redo
6. Quicksave
   1. Saves your map on a list of quicksaves.
7. Open map selection
   1. Opens a better saving/loading menu

## View Menu

This menu contains all options relating to menu, HUD and view modes.

1. Reset position to 0
   1. Resets the camera position, zoom, and rotation to the initial values.
2. Layer view mode
   1. Hide determined layers.
3. Hide UI
   1. Screenshot friendly feature.
4. Camera options
   1. FOV options, camera speed, rotation speed.
5. Map editor settings
   1. Keymap settings, debug options.

## Map Editing Modes

&#x20;The map editing modes are menus to select the list of objects that can be selected to place:

1. Upper
2. Lower
3. Items
4. Scripting & Placements
   1. Spawn placements, random item spawners, triggers.

## Map Editing Subcategories

### For the Upper mode:

1. Flooring
2. Turfs
3. Doors
4. TileObjects
5. Wall Attachments

### For the Layer mode:

1. Piping
2. Disposals
3. Base tiles

## **Items**

1. Items. Bananas, sodas, janicarts.

## Scripting & Placements

1. Spawn placements
2. Random item spawners
   1. Triggers.

## Object List

This menu contains the selected list of objects based on the map editing modes and subcategories.

## Search Bar

Panel containing a search bar to search usign tags, names or keywords
