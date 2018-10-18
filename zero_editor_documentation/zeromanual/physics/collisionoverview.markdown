
 #  Collision Detection and Resolution
The physics system has a set of governing rules for how collisions are detected and resolved. It is important first to distinguish between detection and resolution. Collision detection is the act of determining if two {icon university}[[../Colliders | Collider's]] collide. Collision resolution is the act of updating velocity, position, etc... to realistically simulate an impact. If no collision is detected then no resolution can happen.

 #  Basic Collision Types
The physics system has a few basic rules to determine which of these collision stages a pair of objects can reach. Collision detection is not possible without a Collider as a Collider defines a shape. A [DynamicState](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#rigidbodydynamicstate) property controls how the physics system views a RigidBody. These states show a basic view of the collision detection stages in physics:
|                          | No Rigid Body | Dynamic Rigid Body | Static Rigid Body | Kinematic Rigid Body |
|                          |---------------- | ---------------------- | ------------------- | ----------------------- |
| **No Rigid Body**        | Not Detected
| **Dynamic Rigid Body**   | Resolved        | Resolved
| **Static Rigid Body**    | Not Detected    | Resolved               | Not Detected
| **Kinematic Rigid Body** | Not Resolved    | Resolved               | Not Resolved        | Not Resolved


There are more complicated rule sets that go into fully determining if objects should detect and resolve collision. The simplest examples are the Ghost checkBox and CollisionGroup resource properties on Collider.

 #  Collision Response Factors
There's a few ways to alter how collisions are resolved. The primary way is through a Collider's [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/physicsmaterial.markdown) property which defines density, friction, and restitution.

RigidBody also contains properties that affect collision resolution. A RigidBody's mass is auto-computed from the relevant Colliders' volume and density. To override this manually see [MassOverride](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/MassOverride.markdown). Additionally, various mass properties can be "locked". The {nav icon=list, name=Mode2d} property will restrict the object to simulate 2d movement. Additionally, the RotationLocked checkBox property locks the rotation of a body without changing linear movement restrictions. This is common on objects like a player where rotation would result in undesired game mechanics.

 #  Resolution: RigidBodyDynamicState
RigidBody defines the DynamicState enum property that changes how the dynamics, or resolution, for an object is handled. The default state of a RigidBody is dynamic (i.e. the body is free to move and resolve as normal).

Commonly, a body needs to be locked in space to behave as some fixed world geometry. One way to do this is to remove the RigidBody. Additionally a RigidBody's DynamicState enum can be changed to `Static`. This object will be treated as an infinite mass object that doesn't move. The difference between these two forms of static is mostly internal performance. The general rule of thumb is: if it always exists and never moves, remove the RigidBody; otherwise, mark it static.

A RigidBody can also be set to `Kinematic`. Kinematic is an infinite mass object like `Static`; however, it also gives the physics system extra information about how to resolve collisions. A static object is never expected to move, so if it is teleported by the user into contact with other objects, then the physics system doesn't know how to properly resolve the collision as no velocity was involved. A kinematic object tells the physics system to approximate the velocity in the collision based upon the last and current position of the object. This is typically used for moving platforms or other moving, infinite mass objects.

 #  Collision Information
Information about collisions can be found in two ways. The most common is to listen for [CollisionEvents](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/CollisionEvents.markdown). Additionally, Collider exposes the Contacts property range.

 #  Collision Groups
Advanced control of collision filtering and events can be configured through the use of [CollisionTables and CollisionGroups](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/collisiongroupsandtables.markdown).

 #  Advanced
There are several advanced topics that can affect how physics deals with collision.
 - [Hierarchies](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/Hierarchies.markdown) can be used to make complicated physical objects from simple pieces.
 - [Joints](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/Joints.markdown) allow additional constraints on how an object is allowed to move.

 #  Troubleshooting Collisions
Sometimes collisions don't happen or behave differently than a user would expect.
  - [WhyAreTheyNotColliding](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/whyaretheynotcolliding.markdown) is a helper function to figure out why a collision didn't happen.
  - [Edge Catching](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/edgecatching.markdown) is a common issue when trying to make a player that can cause jarring movement.

---

 #  Related Materials
 ##  Manual
- [RigidBody.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/RigidBody.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/Colliders.markdown)
- [PhysicsMaterial.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/PhysicsMaterial.markdown)
- [MassOverride.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/MassOverride.markdown)
- [CollisionEvents.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/CollisionOverview/CollisionEvents.markdown)
- [CollisionGroupsAndTables.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/CollisionOverview/CollisionGroupsAndTables.markdown)
- [Joints.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/Joints.markdown)

 ##  Reference
- [Collider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Collider.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/RigidBody.markdown)
- [PhysicsMaterial](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PhysicsMaterial.markdown)
- [MassOverride](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/MassOverride.markdown)
- [CollisionEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionEvent.markdown)
- [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionGroup.markdown)
- [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionTable.markdown)
- [DynamicState](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#rigidbodydynamicstate)
 

 