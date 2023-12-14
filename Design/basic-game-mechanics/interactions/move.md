# Move

Moving an object implies different things depending on the object you're trying to move.

1. Pick Up - the character takes the object with their hand, picking it up, and carries it with them.
2. Grab - the character grabs hold of the object with 1 or more hands, to pull/push or even strangle.

More accurately it depends on the size of the object you're trying to move.

<details>

<summary>Examples of small objects</summary>

* Most items; tools, clothing, food, weapons, building materials, etc.
* Small furniture; stools, blender, cell charger, etc.
* Small entities; lizard, birds, cockroach, fish, cats, small robots, etc.

</details>

<details>

<summary>Examples of medium objects</summary>

* Large items; large boxes, large sacks of vegetables, etc.
* Medium furniture; chairs, microwave, small crates, etc.
* Medium entities; humanoids, dogs, medium robots, etc.

</details>

<details>

<summary>Examples of large objects</summary>

* Most furniture; fridge, large crates, water tanks, lockers, tables, etc.
* Large entities; cow, goat, xeno queen, etc.

</details>

So how do we decide when to pick up and when to drag? We check the number of available hands..

* small objects - always pick up
* medium objects + one free hand - drag
* medium objects + two free hands - pick up
* large objects - always drag
