# Shape

### Proportions

This section is immensely important to maintain consistency with our art style. Follow what comes after this sentence like gospel: Stylization involves emphasizing the defining parts of an object. When modeling something that exists in reality don't try to accurately reproduce it, even with reference the goal is just to make a caricature of the real thing. Another thing to keep in mind is that the world the characters inhabit is vastly different from the one that we do. When your fingers are thrice as thick as those of a human, the design language of everything you interact with changes dramatically to accommodate.&#x20;

Just because you modeled that fancy AK-47 as accurately as you could, it can't be usable in game simply because the characters wouldn't even be able to comfortably hold it. Its stock would be too long and makes holding it awkward, and the trigger guard wouldn't even let a finger through. objects that would fit comfortably in our hands like a multitool, would be miniscule and hard to use for the game characters if they got their hands on it. If a single word could be used to describe the design language of everything in SS3D, it would be 'chunky'. Thick edges, large buttons, etc. In the image below, you can see just how different the character looks like compared to an anatomically correct human. Ensure you take this into consideration when making the assets.

![](../../.gitbook/assets/7db283ca36d075a71180f4b3cf95dad0.png)

## Shape

Remember that items will be seen from pretty far away, so zoom out early and often, and always look at your work from all angles.&#x20;

![](https://lh4.googleusercontent.com/OR7j1GP7RnsZ9VBp9E2x4fA8UPFumg96DUUl4Z0vbrg54jJ3Co9BRemiKA60egF9t83L-vzPjju98NA1dfmfQSQ0MMB7K-lFU8iwTgHAEzfhVWwfwpMFFRNosSUoMK87Eo4-HIk5FGSfZmOswmT1Gw)![](https://lh6.googleusercontent.com/3a5EEc74F\_UZqQqthG\_\_\_KiLNPfFjrgI3sLqyGp8bnRGd4YS6mV8mczkSpLk0Z4KR-WZqhhIg5S8Ma7MTH5ihvkSzptV0PuiURv6BkeZZNVMZeKiwfv6zrgKSxJJ6W7AlQl5rRxfax2o4EyDOFQL7w)

### Detail

Focus on details that contribute to the silhouette. A gun barrel or tube doesn’t need to be hollow, it’s enough if the end cap is a darker color or just solid black.&#x20;

If certain details are important but too small to be noticeable, make them bigger.&#x20;

As a poor example, you don’t need 101 keys to model a keyboard the same way you wouldn’t draw every brick in a wall, just enough so that it’s readable as one, and big enough that it can be seen from far away. Don’t get attached to close shots of your model.&#x20;

Too fine or complex detail might just become noise when viewed from the proper distance, so zoom out often.

### Polycount

The current year is ~~2018~~ and modern computers are capable of rendering millions of triangles per frame.

Low poly is largely a stylistic choice, but SS13 is a sandbox game and it’s not unreasonable to expect that hundreds of objects could be on screen at the same time.&#x20;

It’s also about consistency— objects that are very polygon-dense will look out of place next to their low-poly friends.

![](https://lh5.googleusercontent.com/B8Ng2l48\_ocIF4\_XBjFFx5Nr2ZCF7ne2kSDfnYUcAgfbjDVfKHmShinm1ytzM2Q9Wi7s6ZLM4IK51K37dGh51tDzy62raDfEGq2gdeC3gHzRvYBmE9znS\_P7JWYC9v-XYouFmtjXOBOjG5bZXQI5Lg)

### How many sides should my cylinder/sphere have?

Enough that it looks like a cylinder from camera distance. Larger objects have more sides, as well as objects that should have glossy highlights like the cryotube on the right.&#x20;

It's difficult to correct this later in the modeling process. Remember to turn on smooth shading by selecting all faces then using Ctrl-F > ShadeSmooth. Select a matcap from the Shading panel on the right, regular Blender lighting is distractingly shiny and bumpy.

Matcaps don’t affect the material whatsoever, it’s just a preview within Blender.

### Bevels

![](https://lh6.googleusercontent.com/zlgNN209BSJVEJkbQOnZdDdaK0u7RkSYdrfi6e8vTqx0GcAof-yMU8xemzM-zJPUHsDWpZoxuoCSFGAYm4KlzjtT6TOxCZ5-sQs4W\_gXWK5osf0lP5prDNB3CmsO901y1rLCZq75PKBnsb-R\_CtgsA)<img src="https://lh6.googleusercontent.com/MlqE5hUs-CbPAQeuBsbYtWPhhvIgiraAAbdn_gDgDgbH7I0pgK9RBtgxsDmBd6LwtiRyTmgsonWECrwAiA_QM2KsjP0FCc_TpqPR8m6CpLeTI2O-FYrEqOIoDXbw459diROQ9ojtKKDLtoMLyoIYqQ" alt="" data-size="original">

Bevels are very useful in hard surface modeling since they catch and reflect light, highlighting the edges of an object.&#x20;

SS3D though has a rough clay look, with left smoothness as a special eect for things that really need it so bevels are not that important and mostly optional. Do add them when your object has large surfaces, like a fridge, which otherwise would look like a tall box.

Small objects or small parts of larger objects don’t need them, since it would have little impact on the silhouette.

#### Bevel Modifier

Alternatively use the Bevel Modifier in combination with bevel weights, which you can set individually for edges in the model.

It’s easier to tweak but I recommend applying the modifier after you’re done with it.

![](https://lh3.googleusercontent.com/6CJfVN1mCGlYOP5Tg7aTgzIQbYXkixxejWH3dFeHjfNsY4IBLibLStPXvBAMbBSw5zOhGmIdSN7fS77bD2So-SrYbvBUvJp7agDyvfZB42DWdm79O472ZO4f7lfsqCVzjs25yK-KBeGEAXONSSiQEg)
