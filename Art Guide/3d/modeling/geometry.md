# Geometry

## Geometry

(Most of this should be elaborated on at some point.)

#### **N-gons**

* They’re fine as long as they’re at and won’t be animated.

**Triangulating**

* Don’t triangulate your models.

**Inverted normals**

* By inverting the normals of a model you can achieve an interesting pseudo transparency effect.
* It’s not realistic but we’re not aiming for realism.

**Double sided**

* Many thin objects such as paper, leaves or cloth don’t need to have proper thickness, but for performance the engine does backface culling, where faces that are “backwards” aren’t rendered.
* This can be avoided by selecting the mesh, duplicating and then inverting the normals.

**Pivot**

* Always at the center (XZ) and base (Y) of the object.

**Modeling with NURBS**

* Cables and wires, but also some round but geometric objects like the plastic “cup” chair.

**Cell fracture**

* To shatter objects for ingame destruction. Takes some setup.
