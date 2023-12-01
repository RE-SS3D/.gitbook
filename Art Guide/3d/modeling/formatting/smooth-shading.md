# Smooth Shading

This is touched on in the SS3D Style Guide, but it still bears repeating since it's so often overlooked. People often associate low poly art with flat-shaded surfaces, but this is not the case with SS3D! Models in SS3D all have a smooth-shaded appearance, which helps a great deal in getting that soft, almost pastel-like appearance.

![](https://lh4.googleusercontent.com/ZA8FXdTNphxpmcVsrbLLa4hd9C6Va8t9oI\_O7EVdZtjXhg2jvBtXZgW-uirXgfCrO9yjs0WgaYvgyUb\_IFR11rTIX-zyjPEhFTFKADl4LnH3MDgsgNP1ozb8MLa0T5BLKHD5Z3h6MxcEdKT6fJVdPg)

Surfaces in Blender 2.8 can be shaded smooth all at once by entering object mode, selecting your target, and clicking Shade Smooth from the "object" dropdown at the top of the layout.&#x20;

If a sharp edge is desired, you can mark an edge sharp by selecting the edge in edit mode, and clicking Mark Sharp from the edges menu at the top of the layout. Sharpness can also be removed in a similar way, but instead, selecting Clear Sharp from the same dropdown.&#x20;

For best smoothness, try to model using only quads (four-sided polygons). An additional thing to note is that the materials don't use specular highlights, so if you're setting up your own material, **turn specular down to 0**.&#x20;
