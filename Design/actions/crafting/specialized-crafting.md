# Specialized Crafting

Crafting systems such as Cooking or Chemistry are more complex and specialized, due to having a different traditional interface for workstations and the fact of the usage of substance system, and so would require a different approach.

For example, Cooking is based on exposing the materials and substances to different appliances for a set amount of time.&#x20;

## Microwave

An example of the Microwave menu can be seen below:

<figure><img src="https://lh3.googleusercontent.com/lyZrccEWQQY-fccknbApnTyU-YYU3JD7ELlHgtdcC9FVA343yRa-G14Z1JZHwHelbGmPKENeZtelGp5JdpiKD4C7gLMk3UN451DgJTqJSCTaCeQdMZavSVGPmrUXcd8ntZXASdIDRAXytSuC40fe3A" alt=""><figcaption><p>As Microwave oven is a container, It has 8 basic inventory slots (up for a change)</p></figcaption></figure>

A press of a Power button turns of the Microwave and starts the timer, that shows time the microwave started working

At a second press of a Power button, the Microwave stops heating it’s contents and disables the timer

An example of expected behavior:

1. Player places bowl of wet uncooked rice into the microwave&#x20;
2. Player starts the microwave with a press of a Power button and waits for a specific period of time (the diapason mentioned in the recipe list for microwaves)
3. Player stops the microwave with a press of a Power button and removes a bowl of cooked rice from the microwave (player is unable to remove the contents of the microwave without stopping it first).
4. In case the player stopped the microwave too early, the rice stays uncooked
5. In case the player stopped the microwave too late, the rice becomes ruined (contents of the bowl becomes burned mess)

Basically the same goes for stove, oven and chemical burner (the later consumes fuel when used, though)\


## Blender

An example of the Blender menu can be seen below:

<figure><img src="https://lh3.googleusercontent.com/9-xLGn4V9vxige2m_qfpnTUNXDnN8aLs84SkLT6rihxBut69zPqSbU5hPJhZbKHRPTM4fOtJNTF070ixBZJZpy1Rtbf2bF5FwU45fOH_up_mKEguL5ZCh5I5f-LID9FtwT1HqFfH2XmEUeQAso3bhA" alt=""><figcaption><p>As blender is a container, It has a set volume for ingredients and reagents.</p></figcaption></figure>

List of reagents lists only the components of the freshly made reagent, that were solid ingredients and were blended by this blender. (for example, if the mix of vodka and syrup was mixed outside the blender, it would be listed as an Unknown reagent when placed into the blender, but if this reagent is in the blender alongside with strawberries and both would be blended, the reagent list would list strawberries AND Unknown reagent)

A press of a Power button deletes the ingredients, makes a reagent that contains those ingredients (in the same proportions) and mixes it with an existing reagent, if there is one.

Using filled container (like a glass of milk) on the blender, would transfer the contents of the container into the blender

Using empty container (like an empty glass) on the blender, would transfer the contents of the blender into the container
