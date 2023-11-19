---
description: The progress bar of Space Station 3D.
cover: ../.gitbook/assets/SmokingMan_EngineeringGang.png
coverY: 0
---

# 🛣 Roadmap

We use milestones to track large achievements of development. Our [GitHub Projects page](https://github.com/orgs/RE-SS3D/projects) tracks the individual tasks in our active milestone(s). The milestones are defined below.

<mark style="color:purple;">**Purple**</mark> - indicates the milestone is completed.\
<mark style="color:green;">**Green**</mark> - indicates the milestone is in progress.\
<mark style="color:yellow;">**Yellow**</mark> - indicates the milestone is on GitHub but NOT in progress yet.\
**White** - indicates the milestone is only be theorized at this point and will be elaborated on in the future as we get closer to it.

Reminder that our milestones are synced with our release versioning for easy tracking, link below.

{% content-ref url="releases.md" %}
[releases.md](releases.md)
{% endcontent-ref %}

(We will add GitHub links to the name of the milestones in the list below as they get added to GitHub.)



## <mark style="color:green;">0.0 - Rework</mark>

The rework is the first primary milestone. Its goal is to rework the structure (underlying aspects) of the game (such as networking, tilemaps, character movement, etc.), harmonize contributor guidelines and workflows, and porting over necessary systems.

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/7"><mark style="color:purple;">0.0.1 - Server &#x26; Lobby</mark></a></summary>

* [x] Basic server lobby

</details>

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/8"><mark style="color:purple;">0.0.2 - Management &#x26; Documentation</mark></a></summary>

* [x] Starter design documents for major game systems

</details>

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/9"><mark style="color:purple;">0.0.3 - Round System</mark></a></summary>

* [x] Port basic round system
* [x] User ready-up ability

</details>

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/11"><mark style="color:purple;">0.0.4 - Simple Character Controlling</mark></a></summary>

* [x] Character spawning
* [x] Character camera
* [x] Port basic movement

</details>

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/12"><mark style="color:purple;">0.0.5 - Port Interactions System</mark></a></summary>

* [x] Convert to FishNet
* [x] Include interaction wheel

</details>

<details>

<summary><a href="https://github.com/RE-SS3D/SS3D/milestone/13"><mark style="color:purple;">0.0.6 - Port Tilemaps</mark></a></summary>

* [x] Port tilemaps from develop branch.
* [x] Include a tilemap editor.

</details>

<details>

<summary><a href="https://github.com/orgs/RE-SS3D/projects/7/views/1"><mark style="color:green;">0.0.7 - Fixing, Cleaning, Testing</mark></a></summary>

* [ ] Add testing framework, structured logging, playmode & client tests.
* [ ] Fix various basic bugs and networking issues like joining.
* [ ] Harmonize maintainer practices like asset and PR reviews.
* [ ] Document existing systems in the code (not sure what systems need this..)
* [ ] Port google docs for existing systems to gitbook (Interactions & radial menu, Rounds, Lobby/Server)
* [ ] Add new gitbook docs for existing systems (Gamemodes, sprite generation, stamina)

</details>

<details>

<summary><a href="https://github.com/orgs/RE-SS3D/projects/41/views/1"><mark style="color:yellow;">0.0.8 - Character Rig &#x26; Animation</mark></a></summary>

* [ ] New character rig.
* [ ] Basic animations (walking, running, falling, standing, ragdoll, sitting).
* [ ] Server authoritative movement.

</details>

<details>

<summary><a href="https://github.com/orgs/RE-SS3D/projects/42"><mark style="color:yellow;">0.0.9 - Basic UI Guidelines &#x26; Rework</mark></a></summary>

It doesn't need to be 100% fool-proof because we are very early in development and the UIs will be reworked in depth in the future to look nicer and be consistent.

* [ ] Add guidelines for adding UI. Use less hardcoded UI.
* [ ] Convert any current UIs to new standards.
* [ ] Fix numerous bugs

</details>

<details>

<summary><a href="https://github.com/orgs/RE-SS3D/projects/43"><mark style="color:yellow;">0.1.0 - Finalize Rework</mark></a></summary>

Port Remaining Secondary Systems. None of these will be a "piece of cake" but they shouldn't be rocket science either. The systems are already made, they just need to be ported over and any new issues resolved.&#x20;

* [ ] FOV
* [ ] Chat
* [ ] Examine
* [ ] Lighting

Add basic SFX & anims:

* [x] Bike horn
* [ ] Airlock
* [ ] Locker door?

Fixes for the Rework major milestone.

</details>



## 0.1 - Minimal Viable Product (MVP)

The MVP is the goal to achieve a basic demo-like product to showcase a glimpse of our future game. It should include basic health & combat, crafting & construction, clothing, and shuttles.

<details>

<summary>Basic Health</summary>

* [ ] Stamina (already added)
* [ ] Basic hp system (healing + taking damage)
* [ ] Limb severing?

</details>

<details>

<summary>Basic Combat</summary>

* [ ] Throwing objects.
* [ ] Atleast 1 melee combat types (swinging, stabbing, punching)
* [ ] Ranged handgun combat?

</details>

<details>

<summary>Clothing</summary>

Basic clothing system. The belt cannot be put on if the player is not wearing a jumpsuit, and the jumpsuit cannot be removed until the belt is removed first.

* [ ] 5 jumpsuits (cook, security, medic, engineer, captain)
* [ ] 1 belt
* [ ] 1 shoes
* [ ] 1 gloves
* [ ] 1 backpack - **set up inventory for this**

</details>

<details>

<summary>Basic Crafting</summary>

* [ ] Item replacement. Used for many basic crafting tasks.\
  \
  ex. cutting cheese - Using a knife on a wheel of cheese replaces it with 2 half wheels, using the knife on a half wheel of cheese replaces it with a quarter wheel of cheese, doing so again replaces the quarter wheel of cheese with 3 slices of cheese.

</details>

<details>

<summary>Basic Construction</summary>

Basic construction should be somewhat easy i would think. Its something we have had in the past so maybe could use that as reference, also we have in-game tilemap editor so basically it would just be 'hide the editor from non-admins and add some tool interactions similar to that on the develop branch'

</details>

<details>

<summary>Additional Roles</summary>

I agree its not vital but I kinda see these helping with showcasing basic systems. If we have basic health, may as well add a room and clothing and role for it. Bartender represents basic substances, security represents basic combat, assistant represents basic item crafting, engineer is basic construction, captain can 'call the shuttle' to end the round.

</details>

<details>

<summary>Finalize MVP</summary>

* [ ] Basic UIs for gamemode - "You are the traitor!" text for starting antags.
* [ ] Basic UIs for round start - "Welcome to the Station Crew"
* [ ] Basic UIs for round end - "The shift has ended. \[inset sentence describing the end of the round, like the nuke exploding or crew escaping on shuttle]. The antagonists were: \[insert antagonists names and success status]."
* [ ] Add basic shuttles for ability to escape (end the round without the nuke going off). The shuttle should be called via someone using the command console.
* [ ] Proper admin controls - only admins can access the admin controls page. An example of an admin function is the in-game tilemap editor.
* [ ] Add game settings?
* [ ] Add server settings?
* [ ] Lobby chat?

</details>



## 0.2 - Alpha: Expand The Basics

When we really start to expand systems, add interactions, new content etc..

<details>

<summary>Basic NPCs</summary>

* [ ] NPC animals

</details>

<details>

<summary>Expand Interactions &#x26; Containers</summary>



</details>

<details>

<summary>Expand Gamemode &#x26; Rounds</summary>

Expand Gamemodes:

* [ ] Add new basic gamemodes: Traitor + Extended

</details>

<details>

<summary>Expand &#x26; Fix Tilemaps</summary>

* [ ] Various upgrades to the tilemap.
* [ ] Various upgrades to the tilemap editor.
* [ ] Various bugs to the tilemap system, most notably while using the tilemap editor.
* [ ] Add entities to tilemaps.
* [ ] Allow multiple tilemap saves, with naming.

</details>

<details>

<summary>Expand Health &#x26; Combat</summary>

Expand Health:

* [ ] Detachable limbs
* [ ] Basic damage types (brute + burn)
* [ ] Non-functional Organs
* [ ] Basic internal fluids (blood, vomit, saliva)

Expand Combat:

* [ ] Add explosives, with basic damage to tilemaps
* [ ] 2-handed weapons
* [ ] Melee combat - blocking
* [ ] Melee combat - dodging?

</details>

<details>

<summary>Expand Crafting &#x26; Construction</summary>

Expand Item crafting:

* [ ] Item construction. Used in more advanced crafting tasks.\
  (Usually uses object replacement to start the process)\
  \
  ex. crafting a stunprod - (based on TG) Using cablecuffs on a steel rod, replaces it with a stunprod with all the internal objects disabled except the rod and wires. Using an igniter on the stunprod will delete the igniter and enable the internal igniter inside the stunprod prefab. Repeat the process but with a powercell and you now have a stunprod with all the internals enabled.\
  \
  The order for adding internal objects shouldn't matter if they are not dependent on one another. The cablecuffs and steel rod would need to be first in this case because they get replaced into the incomplete stunprod but the powercell and igniter are not dependent on each other so the order they get added after does not matter.\
  \
  Also, each internal object can be removed again using tools so you can fully disassemble your murder weapon after the crime.

</details>

<details>

<summary>Harmonize Clothing &#x26; Character Movement</summary>

Clothing:

* [ ] Add ability for players to strip each other
* [ ] Add more clothing
* [ ] Makes sure clothing works with detachable limbs

Character Movement:

* [ ] Add additional movements: crouching, combat movements, interaction movements, etc

</details>

<details>

<summary>Polish Gamemodes &#x26; Roles</summary>

Polish Gamemodes:

* [ ] Add more gamemodes: Secret,

Polish Roles:

* [ ] Add more roles: bartender, janitor, assistant,&#x20;

</details>

<details>

<summary>Expand Lobbies, Menus, Settings</summary>

* [ ] Character customizer & role priorities
* [ ] Server votes: next round type, next map, etc

</details>



## 0.3 - Alpha: More Systems

Now adding less core but still crucial systems, and expanding previous systems.&#x20;

<details>

<summary>Basic Atmospherics</summary>



</details>

<details>

<summary>Basic Electricity</summary>



</details>

<details>

<summary>More Health &#x26; Combat</summary>

More Health:

* [ ] More damage types (oxygen loss + toxin)
* [ ] Functional Organs
* [ ] Dissolved chemicals in bodily fluids
* [ ] Nutrition?
* [ ] Diseases?

</details>
