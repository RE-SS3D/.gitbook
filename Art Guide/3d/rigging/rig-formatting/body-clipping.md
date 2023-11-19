# Body Clipping

When weighting clothes to the armature of a character, it's often very difficult to ensure that it deforms 100% consistently with the body underneath, resulting in parts of the body clipping through the clothing.

<figure><img src="https://lh4.googleusercontent.com/ssfcKxDyrKs9_WrPkhzCKpwIl13lnN54eYrpBXsj6XZCyQZiO4lnH4Wq1h5YBwo7Gn6fBre6VMuRF0cvG_20Gxc-Tbcd6QfmYctgGcUzKICeydy_KoWJ2lekGmzoeummCO6MAGSeX846DPYUzfCLs-Q" alt=""><figcaption><p>Sometimes, clothes deform inconsistently with the body.</p></figcaption></figure>

To circumvent this, we hide portions of the body beneath the clothes, so clipping isn't an issue.

<figure><img src="https://lh3.googleusercontent.com/BJLVA2CGIaneFaT8DqcIiFEBJRJg65dBDvGr5mIoSGtI1WMGeIG-YLZkX1ToNHUp-Eo2rSAIU-Toikt7LbCJf4aRfa5Du6ThyFVviagC5tdqplxwPJ9jOrz6g75INpx_ROlOsOr6dy4_RrMz1bAyMP0" alt=""><figcaption><p>Hiding invisible parts of the body can prevent excessive clipping.</p></figcaption></figure>

To make use of this, **it is recommended that you model the ends of the clothes along specific cutting lines**, such as at the wrist and below the shoulder for tops, and directly above the knee and below the ankles for bottoms.

We can also make use of an alternate body mesh that reveals only the area surrounding the neck, so shirts can have some leeway on the size of the collar.

When modeling the ends of the clothes, it's also best if you model inside the ends of sleeves, so if the limb is severed, it will still look natural.
