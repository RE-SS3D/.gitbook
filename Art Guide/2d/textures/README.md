# Textures

SS3D models mostly use a color palette in place of actual textures, as it negates the need to learn texturing and UV unwrapping, helps with cohesion and supports a unique style of SS3D.

For simpler stuff it might be best to use colored polygons, as pictured on a few examples below:

<figure><img src="https://lh6.googleusercontent.com/Gd4ZpSrjmrSLlshrUZZyMCIaHrCrpYknjV_oEyyCBiJUCaSk-rpMw314maD07X7wARaH5mcf05Cr7qoXbnSbP17IGnKMRkE-JxkwIieLknycrL9JxWFz8b78GeC7W_VaWvtHxOMxm6o" alt=""><figcaption><p>An few asian-looking symbols made out of colored polygons.  </p></figcaption></figure>

Do not worry, the render settings make those look seamless, unless the seam is needed. For more info on that, consult the 3D Modeling Guidelines document.

Though do remember that items will be seen from pretty far away, so zoom out early and often, and always look at your work from all angles.&#x20;

## Actual Textures

However, textures may be used for some specific cases. For example, repeating patterns, complex shapes or where cutting up the model to add colors may cause problems.

One of such examples: HumanSeveredLimb.png (256x256) used as a texture for flesh cross section with a bone in the middle.

<div>

<figure><img src="../../.gitbook/assets/UV (1).png" alt=""><figcaption><p>HumanSeveredLimb texture applied to a model</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/HumanSeveredLimb.png" alt=""><figcaption><p>HumanSeveredLimb.png</p></figcaption></figure>

</div>

Another example: a cowhide texture Cow.png (256x256)&#x20;

<div>

<figure><img src="../../.gitbook/assets/blender_wP2UEN4gNP.png" alt=""><figcaption><p>Textured cows</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Cow.png" alt=""><figcaption><p>White cow texture</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Cow2.png" alt=""><figcaption><p>Dark cow texture</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/UV (3).png" alt=""><figcaption><p>Cow texture applied to the unwrapped cow model</p></figcaption></figure>

</div>

Same principle can be applied to models that have too fine details to be modeled yet not enough to create visual noise. Such as clothes.

<div>

<figure><img src="../../.gitbook/assets/BikerJacketBears.png" alt=""><figcaption><p>BikerJacketBears.png texture used (256x256)</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/blender_VECmgsYXwk.png" alt=""><figcaption><p>A leather coat with a logo (tattoo would be explained later)</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/UV (2).png" alt=""><figcaption><p>BikerJacketBears.png unwrapped </p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/UV2.png" alt=""><figcaption><p>The exact model part the texture is applied to</p></figcaption></figure>

</div>

Complex text or symbols can use a transparent texture and placed on a model like tattoos or floor decals.

<div>

<figure><img src="../../.gitbook/assets/BikerChest.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Tiger.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/LaserShark.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Ass.png" alt=""><figcaption></figcaption></figure>

</div>

<div>

<figure><img src="https://lh5.googleusercontent.com/OQAlX-4ilZwt_xo1F3SduX_5VrtuEVY25948ydLTKxxvkAsjlZe8Bad6GUNrSZbIW3A5r1B3ohR4mH8iu7VhmFl1iKCTVpd2J7KO9SBcK_d3AmFj5gl3Tja5UEmQO9gvPqm9GGw00iKk" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/blender_NTGF7ysKh8.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/blender_v47DGD8buk.png" alt=""><figcaption></figcaption></figure>

</div>

Some models can use several texture variants, like cows from the example above. To make the creation of such variants easier, one might create a template to guide others, who might take interest in creating more in the future.

<div>

<figure><img src="https://lh5.googleusercontent.com/SDzJ6d8o2yrvWAafAjJiU2BJ3nfotsFZR_bk_DXFeLublYWTUKOGhwp1H8c-yh_ViGqWPM9BYPVvOeCHKRhlA031naq5eMvDUaLBLWzAMEAr-byjwXZcn-eU8P233VM5GaFYE9jWx4st" alt=""><figcaption><p>A fully textured bed blanket</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/$R2RZAYW.png" alt=""><figcaption><p>A template applied to the model</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/$RIXZCQ9.png" alt=""><figcaption><p>A template file Blanket.png (512x512)</p></figcaption></figure>

</div>

Yet another way the textures are utilized are skyboxes. It is a cube with textures (4000x3000) on its inner faces, used to simulate the sky or similar backdrop around a three-dimensional space. Ours mostly used just for that: space backdrop. But there’s some creativity in creating a skybox for a holodeck (Those are in PNG, 4096x3072):

<figure><img src="https://lh4.googleusercontent.com/Q7z7c9dsdobjQeCmLq0_y_LL_lrEvPpyxaLnSuiH50qK2Z_ZHWEXEjmc-WBxG-aw5NHG0tM1VBUY7nxNZgyE9JZRAdl4SZkSr4TjBftSLX8sN5vpAQtrOlI6_yWD2bsrRH2xvnZ4vq__" alt=""><figcaption><p>A more realistic nebula skybox texture used as a backdrop for the real station</p></figcaption></figure>

<div>

<figure><img src="../../.gitbook/assets/Endless Space Skybox.png" alt=""><figcaption><p>A more cartoonish-looking space backdrop used for a holodeck “space” setting</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Winter Wonderland Skybox.png" alt=""><figcaption><p>A more cartoonish-looking space backdrop used for a holodeck “snow” setting</p></figcaption></figure>

</div>
