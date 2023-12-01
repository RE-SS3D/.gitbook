# Known Issues

This system is very experimental, we are still seeing if this makes sense to use and if this is the best alternative. Please report issues.

* If the database is renamed, the old generated class is not deleted.
* The new way of referencing <mark style="color:purple;">**DatabaseAssets**</mark> via <mark style="color:purple;">**WorldObjectReferences**</mark> only works for <mark style="color:purple;">**GameObjects**</mark> (by design). Ideally this should be separated by type or category, and have a way to not depend on guids, I was thinking on testing some stuff with the localization table for ids.



