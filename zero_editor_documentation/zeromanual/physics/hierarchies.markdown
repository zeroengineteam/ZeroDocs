[ Hierarchies](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Hierarchy.markdown) allows physics to building complicated objects from simpler pieces

 ##  Basic understanding
To understand the basics of hierarchies, it's first important to conceptually understand what a [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/RigidBody.markdown) and {icon university}[[../Colliders | Collider's]] role is. A Collider defines a shape and contains certain physical attributes such as density, volume, friction, etc... A RigidBody gives an object inertia (e.g. mass, velocity, etc...). This gives a few meanings to objects in a hierarchy. If an object doesn't have a Collider, then it doesn't have volume or density, which means it can't contribute to the mass of a RigidBody. If an object doesn't have a RigidBody, then it may have collision properties, but it cannot be moved by physics interaction.

This gives four simple objects configurations:
 - No RigidBody no Collider: Physics doesn't do anything.
 - Collider only: Physics detects collision and resolves collision, but this object cannot be moved by physics.
 - RigidBody only: The object is treated as a point-mass that cannot be collided with. Mass is assumed to be 1 for forces.
 - Both: A regular object that computes mass from the Collider and will be affected by forces, collisions, etc...

The next easiest tree to look at is one with only Colliders. As each Collider only represents another collision volume, this tree would logically be the same as independent objects in the scene, ignoring how the transform data is computed. Physics will not move these objects, other objects can collide as normal, and each Collider defines its own materials for resolution.

The first interesting example is an object with a RigidBody at the root and Collider children.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46360.png)

In this hierarchy, the root has a RigidBody and Collider which implies that the root has velocity and mass. The children just have Colliders which imply that they have collision and could contribute to mass. As a root in the hierarchy typically moves children with it, physics chooses to "attach" the child Colliders to the RigidBody, i.e. the entire hierarchy acts as one RigidBody with multiple collision shapes. Each Collider still retains the properties of its material, such as friction and restitution. If one Collider has a larger mass (from the density and volume) then the root RigidBody's total mass properties will reflect this.

 #  Advanced Hierarchies: Nested RigidBodies
From here a larger nested tree can be built with the same basic structure to make a more complicated object. The tree can even have Cogs in the middle without a Collider. The real question is how do nested RigidBodies affect physics? This ends up depending on the [DynamicState](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate) of the RigidBody.

 ###  Dynamic RigidBodies
When a RigidBody is marked as being `Dynamic`, it signifies that it should be an independent entity that is free to move and resolve as normal. This means that any dynamic RigidBody in the middle of a hierarchy behaves as if its sub-tree was a completely independent object. By keeping the objects in the hierarchy, logical organization is preserved while still allowing free movement. Archetypes can be made from a larger collection of individual objects (e.g. cars and their tires). Additionally, a RigidBody can be quickly toggled to another DynamicState enum.

 ###  Static RigidBodies
If a RigidBody is marked as `Static` then it behaves as if there's no RigidBody in that sub-tree. This is particularly useful if a sub-tree starts static but then switches to dynamic at a later point in time.

 ###  Kinematic RigidBodies
If a RigidBody is marked as `Kinematic` then it behaves like a `Static` body in the tree with one main exception: kinematic implies that an object can apply forces to other objects but cannot receive forces. In this case a kinematic sub-tree can push other objects but will not receive forces back. This can be useful to define a sub-portion of tree for a player to push objects without being pushed back.

 #  Non-Uniform Scale
One common problem with building hierarchies is when a parent object is non-uniformly scaled. This introduces what is known as a skew. Skews are currently not supported by the physics system and will be stripped out of any transformation. Typically all root objects should be configured with uniform scales.

 #  Massless Children
A common scenario when building complicated hierarchies is wanting to add a collision volume for game logic reasons without affecting the overall mass properties of the hierarchy. To do this, the physics systems supports a special configuration on the [PhysicsMaterial](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsMaterial.markdown). If a material's density is set to 0 (this has to be manually typed) then the object doesn't contribute to a RigidBody's total mass.

 #  Troubleshooting
When building a larger hierarchy, each Collider is still treated as a distinct object for collision detection. This means that it's possible for another object to get sandwiched between two flush Colliders (e.g. a table and its legs). Currently no solution is available to prevent this behavior. 

---
 #  Related Materials
 ##  Manual
- [RigidBody.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/RigidBody.markdown)
- [Colliders.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/Colliders.markdown)
- [PhysicsMaterial.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsMaterial.markdown)

 ##  Reference
- [Hierarchy](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Hierarchy.markdown)
- [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/RigidBody.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown)
- [PhysicsMaterial](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsMaterial.markdown)
- [RigidBodyDynamicState](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate)
 
  
  
  
  
  
  
  

 