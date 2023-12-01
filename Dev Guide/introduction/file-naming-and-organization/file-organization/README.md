# File Organization

## /Assets

Most of our project lives in this folder and as a result we need to keep it organized. As you may have guess the folder itself it broken up into various sub folders. Here is the ruling:

<details>

<summary>/Assets/Art</summary>

Art assets are _**"external"**_ assets, meaning they are created via an external source (outside of Unity). EX. pngs, oggs, mp4s, fbxs, etc.. Although some assets will not saved in this folder (materials, shaders, etc.) because those assets are exclusive to Unity and were not created externally (see the "Content" folder below).

Due to the nature of our project being open-source and having a community of contributors with various skills, we have segregated the Art folder by asset type, using the following sub-folders:

* **/Animations:** 3D animation files for our 3D models.
* **/Fonts:** font files.
* **/Graphics:** 2D images used mostly for UI.
* **/Models:** 3D models.
* **/Sound:** audio files.
* **/Textures:** 2D images and animations used as textures on 3D models in-game.

This helps reduce clutter in individual folders and also some assets are used in combination with multiple other assets in various ways.

Next we sort the art assets by [Object Type](object-type.md). This applies for all of the above folders except Graphics and Fonts because those are mostly for UI.

Most files in the Art folder are documented in the Art Asset Contributor list currently saved on our Google Drive.

</details>

<details>

<summary>/Assets/Content</summary>

**Content assets are '**_**internal**_**' assets**, meaning they are created within Unity itself. EX. shaders, materials, prefabs, etc..

Unlike art assets, content assets, are **NOT** sorted by asset type, but rather their broad usage.&#x20;

* **/Addressables:** asset data files.
* **/Data:** Holds all the **Scriptable Objects** and data files that are used by scripts.
* **/Resources:** you will see a Resources folder here in the Content folder and maybe a few floating around other places in the project. This is used to house files that specifically require to be held in a folder called resources. I think this only effects 'object type' content assets. I think it had something to do with network IDs or the tilemap or both (Broodje would know).
* **/Scenes:** unity scene files for menus, maps, and such.
* **/Systems:** technical content relating to game systems like, substances, UI, controls, etc.
* **/WorldObjects:** all the prefabs and related content that make up our interactable in-game objects. This folder is sorted by [Object Type](object-type.md)!

</details>

<details>

<summary>/Assets/Editor</summary>

_<mark style="color:orange;">**Editor assets do not go to built executables!**</mark>_

**Editor assets are files exclusive to Unity editors**. EX. the tilemap editor, or atmospherics editor.

</details>

<details>

<summary>/Assets/Scripts</summary>

**Scripts are code files that make up our codebase.** This includes things such as UI code, networking code, camera & FOV code, game systems, etc.

They are separated by two main folders, SS3D and External:

* **/SS3D** holds all the scripts made by us, it is our codebase.&#x20;
* **/External** is where we put all the tools and frameworks we use, and that are not created by us.

</details>

<details>

<summary>/Assets/Settings</summary>

Holds all the **Scriptable Settings** assets, which are global settings that can be custom created.

</details>

<details>

<summary>/Assets/StreamingAssets</summary>

This is for file saved by the game, like map saves.

</details>

## /Builds

This folder is for storing builds and their related assets like .bat files which we currently use for running the game as a developer.

## /Documents

Documents is simple, it stores the basic documents for the repo.

## /ProjectSettings

ProjectSettings stores all various settings and managers for the project.
