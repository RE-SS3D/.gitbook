# Value

## Value&#x20;

Value is brightness independent of the color you use. If you were drawing a picture that would be the end of it, but in 3D, value is a function of the shape of your object and the lighting ingame, which could come from any different angle.&#x20;

You can’t control lighting, but the shape of the object is up to you. If computers could draw an infinite amount of polygons you wouldn’t have to worry about anything else, since you could just perfectly describe the surface of any object.

<img src="https://lh6.googleusercontent.com/7Dbi75EsQFxDsu2oKZEm2OjcfXoCN4WgOm_DCUOQ0dDooMXXVzy-HFdGOHM3i1QCPb7cbwHbkHUa2YlNsy9mM5z5CK8-S6tzaOlE0cTVXDVuMOdxcmPFyGrbir_jxFM1ZvSNnuSQhVGAYczHVGDR5A" alt="" data-size="original">

### Normals

But we have a limited polygon budget so we rely on normals to make up for it. Normals are just the direction the surface is facing, which by default is straight up from each individual face.&#x20;

By tweaking these directions you’re “bending” the surface even though its shape hasn’t really changed.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Mood in a single SS13 round can vary wildly, and lighting needs to lend itself to both calm and spooky situations. Under regular conditions, like well lit Medbay or hallways, objects are fairly uniformly lit so normals aren't that big of a deal.&#x20;

This is intentional as the skill floor for creating new assets shouldn't be high. The exception to this are objects with large at surfaces, which can look pretty different.

### Sharp Edges

Sharp edges are hints for Blender to do the normal splitting for you. Setting sharp edges is very easy, just put them down wherever there should be a discontinuity in the surface.&#x20;

The base of a bolt sticking out of plating, two different materials making up the same surface, or the seam where parts of an object would be welded together.

![](https://lh3.googleusercontent.com/DzTN4kuhl5KuOvpgAB9k2WGJ8jc-kPL\_6\_G5zfJ-vX3f3nr1rYqDRtEp7IKgEPpO0rFpUD9yombGjSlcmyGyB1uI230D0wDARNQ48mkzPyEA\_\_g-YuJ2hJJO-xeyrXZHL6\_Z9pz-6GwGdS2T9\_tPug)

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Some examples: The tubes going into the cryo don’t need it, since sharp edges are used to split continuous meshes and the tubes are separate from the base.

![](https://lh6.googleusercontent.com/C11vTnC05Dp7LAn43Qn8kJ9y65GFlCkbwtQM3oL4LQyQQOLOp4vu3Hg5SbhUMuxsFCEdvNbTTjvALTDN3PLKvq65qwVdJ8hkPoycdib0dOZqkjj3CCDIOsRxl\_CiJ1QGmctZGeoTiwNXDUPsTiDbfw)![](https://lh5.googleusercontent.com/82FuDLABnJYwFvT4cwC0P9wH9i2G0O63y5lexz1ohUIg3DF2iYZ6r6A4D\_im2OJV0MYOcT19y41M0Jd1oE-GiXwjFCJRqAF\_nbUYvTm7Z15k2X8P94McJ5eKfgKmiDE2NUJdNM3dpJyAbpXUwg6ioA)![](https://lh6.googleusercontent.com/YZes9wccMxyNGOi6XdlnVOWcEqJdog6Sad-yZhhKvMEwrRqtDQgvHUhPd7D9LDu-keqALjiL72Fk23CwUV7M8sNPzd98CF3gUbuLKAUoQ5aeZ4EVc3mG1HRGo3SHTWJYS3DsRec8j6y9GIolt1WFrw)![](https://lh5.googleusercontent.com/JFCC5LtlivjwflZP2PztFTje8YlMf9h6BQFqwPMgcPCbPAD9RcDx91X7B6UlT7AliW6BMkGPVGWgf14yDh\_NzhAPO6ltmwrbBamiQtG9nhsHUBqP9OemCxRUDKaU2Z4mFA8IpBu3FOT\_Dr-N1ntwHw)
