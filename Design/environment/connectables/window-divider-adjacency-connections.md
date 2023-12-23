# Window Divider Adjacency Connections

As the name implies, window divider connections are specific to creating seamless windows and use the “Window Divider Adjacency Connector”.

The window divider adjacency connector is not meant to be used with the window models themselves, it is meant to be used with the “window dividers” component that overlays the windows. The reason for this is explained when we look at the sheer number of possible connection variations a single window tile can have. Initially there may not seem like many, but it becomes apparent when looking at the more complex shapes (“T” & “X”).

After carefully considering all possibilities, we reduced the total number of possible variations by counting any corner connection as a wall (regardless if it is a wall or window) if at least one of its adjacent connections is a wall (these specific corners are marked with purple in the image linked below). Next we discarded any shapes that would be a duplicate of another shape when rotated. After these reductions we are still left with \~170 possible connection variations between our metal walls and windows. This would also mean that there would be another \~170 possible models for EACH type of window (window, reinforced window, plasma window, etc.).

<figure><img src="../../.gitbook/assets/Possible Window Connections.jpg" alt=""><figcaption><p>Image resolution too large, open separately in <a href="https://drive.google.com/file/d/1pSht_baAn3uyGBjYhmiWuukVFa7VNAsn/view?usp=share_link">https://drive.google.com/file/d/1pSht_baAn3uyGBjYhmiWuukVFa7VNAsn/view?usp=share_link</a></p></figcaption></figure>

Using separated components, we are able to use just 23 window divider models with the 15 window models (using the advanced adjacency connector). Reinforced windows can use the same dividers, so they simply only require 15 models themselves. Adding a new exotic type of window (ex. gold) would require 15 gold window models as well as 23 gold window dividers for a total of 38 models, far less than 170.

<figure><img src="https://lh3.googleusercontent.com/WMDH8jKXsVP6fsHGR0WfMd3Bn8a6vOCBP6h9RjOv804uc15GCNbPoYkgK-OZpv_2n_OBKe5swfLV5D_CWW3XURDV4bjTWQkM1aEeE7N-q5fku9vBdp_gE-73M9QbcCCQ-OsjlW_Jnc2eZNzT8JRrvg" alt=""><figcaption><p>Window dividers can have different styled edges and can wrap around internal corners.</p></figcaption></figure>

The edges are pretty self explanatory, “flat” are used on flat walls, “angled” are used on corner windows, “full” are used to extend the divider to the next tile (basically no edge).<img src="https://lh3.googleusercontent.com/rjMRRxTXqBjiDU2Tqjv3VTGi4aWdsGpAFxio9M-JIn2A6aiD7CWaL2erqBoJ0KiSyA4Xf2FyD9ELj9UnI18m_wkOq9FnjVzyIQVZcodFjaec8i3HVqOQ85SiMYcawUqMha1XNZhTXnG1ucg_3PboWw" alt="" data-size="original">![](https://lh5.googleusercontent.com/5PesH3id2Jwyy78iWkj2YOyEu0YD-yeLrcRyNo8U1\_-nVDBe56jzcB6pU36OuuMYVyGy755OsFKCSVJiH1rU5mx0bdci3SJriVK3cviKt6IEMMXuNx7jzq49BbI5Due8b3ibv6V0yWJF8hmjFaZgZw)![](https://lh5.googleusercontent.com/kAMGVIkCwsXtAUyEzLCSBKvbqwSKU9XOxeJbqMkz9wd4Kh52e9PlvXt4YAs5t\_6PbheO\_FeN0n182Z\_AxUhFBr9DpU317XfXtfVsSq0KlekpQhaNjvCxNUptb\_XUQsxVVx7A\_igG8g7KqYly\_hSyWg)

\
The wall dividers are named based on how many sides they overlay. They are defined below:

A - A variant that overlays 0 sides but does overlay 1 corner (NE).

B1 - Overlays 1 side (N), both edges are flat.

B2 - Overlays 1 side (N), both edges are angled.

B3 - Overlays 1 side (N), both edges are full.

B4 - Overlays 1 side (N), left edge is flat & right edge is angled.

B5 - Overlays 1 side (N), left edge is angled & right edge is flat.

B6 - Overlays 1 side (N), left edge is flat & right edge is full.

B7 - Overlays 1 side (N), left edge is full & right edge is flat.

B8 - Overlays 1 side (N), left edge is angled & right edge is full.

B9 - Overlays 1 side (N), left edge is full & right edge is angled.

C1 - Overlays 2 sides (N & E) and their joining corners, both edges are flat.

C2 - Overlays 2 sides (N & E) and their joining corners, both edges are angled.

C3 - Overlays 2 sides (N & E) and their joining corners, both edges are full.

C4 - Overlays 2 sides (N & E) and their joining corners, left edge is flat & right edge is angled.

C5 - Overlays 2 sides (N & E) and their joining corners, left edge is angled & right edge is flat.

C6 - Overlays 2 sides (N & E) and their joining corners, left edge is flat & right edge is full.

C7 - Overlays 2 sides (N & E) and their joining corners, left edge is full & right edge is flat.

C8 - Overlays 2 sides (N & E) and their joining corners, left edge is angled & right edge is full.

C9 - Overlays 2 sides (N & E) and their joining corners, left edge is full & right edge is angled.

D1 - Overlays 3 sides (W, N, & E) and their joining corners, both edges are flat.

D2 - Overlays 3 sides (W, N, & E) and their joining corners, both edges are angled.

D3 - Overlays 3 sides (W, N, & E) and their joining corners, both edges are full.

D4 - Overlays 3 sides (W, N, & E) and their joining corners, left edge is angled & right edge is full.

D5 - Overlays 3 sides (W, N, & E) and their joining corners, left edge is full & right edge is angled.

E - Overlays all sides (N, E, S, & W) and all corners except SE.

<figure><img src="https://lh3.googleusercontent.com/14v1r--2WVB-1Z3LbQ2C0rQJdsSWiPrru2YVBnpiu48362ai9eWzqVkBPeZYiasFKhVOy7Nyx3gn0MiIif12HJensqBBZVI795dkE9zIUQYlON1yUVujllJ7cyCKaQFZo59qtPkBn5jJfV7bhY4MLw" alt=""><figcaption><p>Window Dividers</p></figcaption></figure>

_**The window dividers could be made even even more modular but work on this has been put on hold while we further discuss quartering tilemap tiles.**_
