[physicsspace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown) is a component that manages all physics objects within a space.

 ##  Queries: Casting/Events
Most commonly, a user will be working with the PhysicsSpace at run-time through function calls. The most common example of this is to query some collision information about the scene through what is called a cast function. A cast function lets a user query what collision shapes are in a certain region. The most common of these casts is a RayCast which is often used for line-of-sight testing, bullets, and so on. Additional information on casting can be found on [this](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicscasting.markdown) manual page.

In addition to casting, PhysicsSpace supports a limited set of "event casting"; that is, sending a user defined event to all objects with a certain volume. This can be achieved with the "DispatchWithin" functions.

 ##  Collision Filtering
Another important run-time feature of the PhysicsSpace is allowing object pairs to be filtered out of collision through the use of the AddPairFilter and AddHierarchyPairFilter functions. These functions allow per object ignoring of collision (no events will be received) when [CollisionTables](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/collisiongroupsandtables.markdown) are not sufficient, such as ignoring collision with a player and their projectiles.

 ##  Important Properties
There are two important properties to help control behavior of the physics system:
  - {nav icon=check-square-o, name="Mode2d"} sets a global state that determines if objects behave in 2d, i.e. they cannot move along the z-axis and they can only rotate about the z-axis. Individual {icon university}[[../RigidBody | RigidBody's]] can override this if desired.
  - {nav icon=pencil-square-o, name="CollisionTable"} lets the user specify CollisionGroup pairs and how [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) with these groups should interact with collision. This is the most efficient way to setup collision filtering so as to not resolve collisions or receive events.
 
 ##  Advanced Properties
Additionaly, there are several other properties on the physics space that are for more advanced users.
  - {nav icon=pencil-square-o, name="SubStepCount} lets the physics space run multiple iterations for every timestep to increase simulation fidelity.
  - {nav icon=pencil-square-o, name="PhysicsSolverConfig"} allows defining various properties about how collisions are solved with the [PhysicsSolverConfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicssolverconfig.markdown) resource (e.g. baumgarte constants).
  - The static and dynamic broadphase type can be configured for run-time. This is most commonly done to switch the static broadphase to something that allows cheaper dynamic addition/removal of objects at the cost of slightly slower queries.
  - {nav icon=check-square-o, name="Deterministic"} tells the PhysicsSpace to do extra work to produce the same result from the same inputs every time. This is slightly more expensive and can be disabled if needed.
  - {nav icon=check-square-o, name="AllowSleep} should almost always be on, except when trying to debug if there is a logical sleeping bug.
  
 ##  Debugging
A common issue during development is to have two objects not collide when the user thinks they should. To help aid debugging this, physics exposes the [WhyAreTheyNotColliding](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/whyaretheynotcolliding.markdown) function. This function returns a text string as to why the physics system currently thinks these two objects are not colliding.

---

 ##  Related Materials
 ###  Manual
 - [physicscasting.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicscasting.markdown)
 - [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)
 - [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
 - [collisiongroupsandtables.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/collisiongroupsandtables.markdown)
 - [whyaretheynotcolliding.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/whyaretheynotcolliding.markdown)
 - [physicssolverconfig.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicssolverconfig.markdown)

 ###  Reference
 - [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)
 - [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
 - [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
 - [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown)
 - [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown) 

 