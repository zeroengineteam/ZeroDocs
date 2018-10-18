
 #  PhysicsCasting

One of the most common run-time interactions with a [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown) is casting, which queries for all objects within a region of space. This allows common operations such as line-of-sight queries, volume queries, and so on.

Typically a cast will take 3 arguments:
  # The shape to cast
  # How many results to receive at max. This is needed for internal optimizations in physics. For Ray/Segments, the results will be sorted by the t-value.
  # The [CastFilter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CastFilter.markdown) describes how to filter out results when casting. Common operations include skipping objects of certain configurations (Static, Kinematic, [CollisionGroups](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/CollisionOverview/CollisionGroupsAndTables.markdown), etc...).
  
Currently, the physics systems supports a few common casting types:

 ##  Ray Casting
[ray](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ray.markdown) casting checks for all shapes in a direction. Ray casts are common for things like line-of-sight tests.
 ##  Segment Casting
A [segment](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/segment.markdown) cast is like a ray cast except it has an end position. Segment casts are used when there is a known max distance for the cast.
 ##  Sphere Casting
[sphere](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sphere.markdown) casting checks to see what objects are within a sphere. Useful for simple volume queries such as finding all objects within an explosion radius.
 ##  Aabb Casting
[aabb](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/aabb.markdown) casting checks what objects are within an axis-aligned box. Sometimes a box is a better shape for casting, especially when the query area is long an thin.
 ##  Frustum Casting
[frustum](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/frustum.markdown) casting checks what objects are within a frustum. Useful for queries that come from a camera where perspective should be taken into account.
 ##  Collider Casting
Sometimes a more complicated shape query is desired. [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Collider.markdown) casting allows the user to say: "What if this collider was over there". This is commonly used for a simple preventative collision check.

 ##  CastFirst
Ray and Segments have an additional "CastFirst" operation for convenience. These cast functions implicitly have a max object count of `1`.
  
 #  DispatchWithin
In addition to regular casting, the [PhysicsSpace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown) contains other common cast related functions. Sometimes casts are performed just to send events to all shapes within a region. This is common for a generic interaction system where each object may or may-not handle some event. Instead of casting and iterating over all results, the PhysicsSpace has the "DispatchWithin" functions. Currently only Sphere and Aabb dispatch functions exist.

 #  Sweeping
While a cast can be used as a preventative check, sometimes the accuracy is not enough. This is where the `SweepCollider` function comes in. Sweeping can be thought of as extending a collider's volume in a direction to find the exact times that a collision would happen with static objects. This allows writing Time-of-Impact logic to avoid missing any collisions.

NOTE: Swept casts are expensive operations and should be used only when important, such as a player.

---
 #  Related Materials
 ##  Manual
- [PhysicsSpace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Colliders.markdown)
- [CollisionGroupsAndTables.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/CollisionOverview/CollisionGroupsAndTables.markdown)
  
 ###  Reference
- [CastFilter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CastFilter.markdown)
- [CastResult](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CastResult.markdown)
- [SweepResult](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/SweepResult.markdown)
- [Ray](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Ray.markdown)
- [Segment](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Segment.markdown)
- [Aabb](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Aabb.markdown)
- [Sphere](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Sphere.markdown)
- [Frustum](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Frustum.markdown)
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsSpace.markdown)
- [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CollisionGroup.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Collider.markdown)
 

 