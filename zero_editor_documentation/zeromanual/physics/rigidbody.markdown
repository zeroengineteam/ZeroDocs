The [ RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) component defines the inertia (mass, velocity, etc...) of a rigid object (i.e. one that cannot be deformed by forces). RigidBody approximations are used in physics to simplify common behaviors for both performance and stability.

 #  RigidBodyDynamicState
RigidBody defines the [ DynamicState](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate) property that changes how the dynamics (or resolution) for an object is handled. The default state of a RigidBody is dynamic (i.e. the body is free to move and resolve as normal).

Commonly, a body needs to be locked in space to behave as some fixed world geometry. One way to do this is to remove the RigidBody. Additionally a RigidBody's DynamicState enum can be changed to `Static`. This object will be treated as an infinite mass object that doesn't move. The difference between these two forms of static is mostly internal performance. The general rule of thumb is: if it always exists and never moves, remove the RigidBody; otherwise, mark it `Static`.

A RigidBody can also be set to `Kinematic`. `Kinematic` is an infinite mass object like `Static`; however, it also gives the physics system extra information about how to resolve collisions. A static object is never expected to move, so if it is teleported by the user into contact with other objects, then the physics system doesn't know how to properly resolve the collision as no velocity was involved. A kinematic object tells the physics system to approximate the velocity in the collision based upon the last and current position of the object. This is typically used for moving platforms or other moving, infinite mass objects.

 #  Mode2D
{nav icon=list, name=Mode2D} defines whether a RigidBody should behave like a 2D or 3D object. If an object is 3D, it can translate and rotate in all three dimensions. If an object is 2D then its movement is restricted to the xy-plane and can only rotate about the z-axis. By default, a RigidBody will use the {nav icon=check-square-o, name="Mode2D"} state of the [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown) so that an entire space can be changed at once, but an individual RigidBody can be set independently from the space.

It is important to note that Mode2D only affects how the physics system will treat the object. A user can still manually translate or rotate an object on any axis, but physics will be unable to move a RigidBody on the locked axes, even if forces or velocity act on them.

 #  RotationLocked
Sometimes, physics shouldn't be able to rotate an object. In this case, the RotationLocked checkBox property can be used to restrict rotation while still allowing all linear forces to affect the object. This can be especially useful on a player object when rotation complicates game logic.

NOTE: Sometimes dynamics will seem odd (e.g. friction, resolution) on locked objects. This is because humans tend to have bad intuition for physics on objects that can't rotate as this doesn't occur in real life.

 #  Sleeping

Sleeping is an optimization for physics. If an object hasn't moved in a while then physics will not perform some operations unless the object is interrupted (woken up). As this can sometimes cause gameplay bugs, it is a toggleable property. To help debug, there is also a global AllowSleep checkBox property on the PhysicsSpace.


Common bugs involving sleeping include:
 - Relying on events to be sent out even when objects are asleep
 - Forces not affecting the object (even from script)

For this reason, it is not uncommon to turn off sleeping on a player controlled object. Additionally, an object can be manually woken up through the `ForceAwake` function in script. 

Sometimes game logic may rely on sleeping. One such example of this is waiting for all objects to fall asleep to trigger the end of a turn or level in a game. For example, an environment-destruction game where the player's turn ends when all pieces of the environment stop moving and fall asleep. This can be checked both by querying the current state of the RigidBody and by listening for events. On rare occasion, a RigidBody may need to be forced to sleep (e.g. after some global timer) through the `ForceAsleep` function.

 #  Movement via Script
A RigidBody is expected to be moved through the use of physics instead of manually being teleported via the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown). There are a few common methods to do this:
 - **Forces**: forces allow pushing an object over time while taking into account the object's mass. The same force applied to a heavy object will cause a slower change in momentum. Forces are accumulated each frame (such as gravity and drag) and are applied once physics updates.
 - **Velocity**: velocity describes how many units per second this object will move. This can be manually changed in script to control how an object moves. Changing the velocity directly will not take into account the object's mass.
 - **Impulses**: an impulse is like a hybrid of a force and velocity. An impulse is defined as an instantaneous force, i.e. a force that will be instantly applied to velocity. Use impulses to immediately update an object's velocity while still taking mass into account.
 
All of these are applied by default to the center of mass of the RigidBody. This means that linear values will not affect angular values and vice versa. The linear and angular values, however, can be independently applied (angular force is called torque). Additionally, there is an `ApplyAtPoint` and `ApplyAtOffset` function for all three application methods. These apply a force/velocity/impulse at a world point or world offset vector that will result in changes to both linear and angular momentum.

---

 #  Related Materials
 ##  Manual
- [physicsspace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown)

 ##  Reference
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [ DynamicState  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate) 

 