# Outward Normals

A "normal" is the direction the face of a model is pointed. In the images to the right, the normals are represented by the blue lines.

![](https://lh3.googleusercontent.com/rSREJjpmtSTGPxO09FPgtzGrp80iIsV7KB\_wMy73VrPv8TG0lqqDUxmsq2BtSIiQDfT1mcUoVMbu\_-WEYFKl5MS6rvQmoJJENAT7FDd9UkCjvpyXuG1tjoFXrPKsgZgBNpi0HobfeTY3386V-vBkLg)

To save processing power, software like Unity will only render the "normal" side of the face. This process is called "backface culling".

By default in Blender, backface culling is turned off, so it will render both the front (normal) and backside of each individual face. This commonly results in models that have faces with inverted normals, since, to the modeler, the faces appear to be all the same.

This can be prevented by enabling backface culling in Blender. As of Blender 2.8, backface culling can be found in the material settings while in LookDev view.

![](https://lh3.googleusercontent.com/CNYVpeRMaW2WLNv5qO3\_l9b4L6r7YtgcMQpz4ngtNbpGZFooHbvgIYdP87nTFSJo27liNtSjHRQqs9IEllO-D\_-p5M0IGqFqvTMs1ep00hmUsef8ALSz1iMecmvFcdWGZQIPlvuc6itXZ-cO2KUNtA)

The template in the SS3D modeler's kit has backface culling enabled by default for all present materials. Hopefully taking this step and allowing backface culling should allow modelers to keep better track of the normals. Keep these fundamentals in mind when modeling flat objects like paper, as they will need to be double-sided.
