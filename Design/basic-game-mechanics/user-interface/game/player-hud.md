# Player HUD

The player hud will be dependent on a few factors, with differences in the UI elements based on those factors.

* Admin: has special UI elements for special functions.
* Player: the most common user.
* Species: Species refers to what kind of character the player is controlling which determines the UI appearance and layout (e.g. a ghost wont have clothing, hands, etc. but a human will).
* Role: Some roles may have unique abilities or inventories thus having some UI differences (e.g. a changeling scientist will have more abilities and UI options than a regular scientist).

Human HUD example below:

<figure><img src="https://lh3.googleusercontent.com/fVNB8adNvc5R26K1tPW_WAXzl-m0Wf9nr8TAgULFhNr1afyseDgktzrJTfQ38gKthBSExrvrxRUC2BH67FGc8qEWGAmC-JKlo0JrMULeZS7tZ5bqXzDJVf4fubV1XccToDAbZZQwMYjOW8uSvXeZqA" alt=""><figcaption><p>Image taken from the 'outdated' branch.</p></figcaption></figure>

The player’s interface will likely be the most important part of the average game. The following is a breakdown of what is seen above, starting in the bottom center of the screen:

* <mark style="color:yellow;">**Hands**</mark>: These icons represent what is currently in the player’s hand. The active hand is lit up, while the inactive hand is dimmed. When a player picks up an item in the active hand, an icon should appear in the players’ hand representing said item.
* <mark style="color:yellow;">**Pockets**</mark>: To the right of the players’ hands are their pockets, which are concealable storage for small items that can fit in the players’ clothes. If the player doesn’t have clothes with pockets, these slots will be dimmed, and inaccessible.
* <mark style="color:yellow;">**Storage**</mark>: To the left of the players’ hands is storage. This is where the player will be keeping their ID, tool belt, and backpack. Items of the respective types can be put into these slots for easy access. The player’s ID determines their level of access across the station, whereas tool belts and bags can store objects within them.
* <mark style="color:yellow;">**Hover Text**</mark>: This is part of the examine system and displays the name of the object the player’s mouse is hovering over.
* <mark style="color:yellow;">**Clothes**</mark>: On the bottom left of the screen, the player can see what they are currently equipped with. Here, there are slots for shoes, jumpsuits, gloves, overcoats, ear-wear, masks, glasses, helmets, and one slot of suit storage for larger objects like rifles or oxygen tanks. A toggle also exists at the bottom left, for collapsing this menu.
* <mark style="color:yellow;">**Intent**</mark>: Near the bottom right of the screen, the intent indicator is a toggleable button which shows the player how they will be using their active hand. For example, if the player has a screwdriver in their hand in “help” intent, clicking a vending machine may open a maintenance panel. But, if the player has the screwdriver in “harm” intent, the player may do damage to it.
* <mark style="color:yellow;">**Targeting Doll**</mark>: To the direct northeast of the intent indicator is the targeting doll. The player can click various parts of the doll to indicate what part of a humanoid the active hand will be targeting. For instance: should the player find themselves in a fight, stabbing a player in the eyes would be strategically different than stabbing their feet.
*   <mark style="color:yellow;">**Chat**</mark>: The chat is at the top left of the image above, and is arguably one of the key points of the game. In-game, this window can be dragged around the screen to suit the players’ needs. The chat contains all manner of information about the world around them, including player dialog and emotes, a log of actions, and even what your character may be thinking. On the station, different methods of communication exist between different departments.\
    A medical officer probably doesn’t want to hear about the delayed shipments in the cargo bay, so different communication channels exist. For this reason, the player may create custom tabs that isolate specific communications for easy readability.

    The text in this game is rich. For example, text outputted by a robot is highly likely to be different than text outputted by a clown. Or, text by someone who is g-g-gg-ett-t-in-ng el-e-ect-tro-c-cute-ed may read differently than someone who is ssslightly more ssscaly than others.

    A person may have “said'' something, but a spider may have “chittered” something, and so on.
* <mark style="color:yellow;">**Toggle UI**</mark>: Should a player wish to have a little less clutter on the screen, at the bottom right there are toggles for displaying the chat and targeting doll windows.
* <mark style="color:yellow;">**Announcements**</mark>: Announcements are located to the right edge of the screen, and are messages that the station commanders feel are necessary to deliver to the entire station. They will remain on-screen, unless the player clicks the megaphone button, which should hide the message.
* <mark style="color:yellow;">**Warnings**</mark>: The station is a dangerous place. At the top right of the screen, a list of warnings may be present for the player, that may influence how they choose to play. For instance, pictured in the image above: the air pressure in here is way too high, and it’s way too cold! While most warnings exist to indicate hazardous conditions, it may also indicate other features regarding the status of the player character, such as whether or not they’re buckled into their shuttle seat, or whether they’re unconscious.
