The physics system allows collision and inertia to be defined on objects. This is primarily achieved by the Collider and RigidBody components. Additional manipulation of object movement can be achieved though PhysicsEffects and Joints.

 #  [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown)
The PhysicsSpace is where all physics components live and interact together. The PhysicsSpace contains data to describe how objects should interact together. It also contains helper functions to query information about a space, such as cast operations.
  
 #  [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Rigidbody.markdown)
RigidBody defines the inertia properties (e.g. mass, velocity) of an object. This helps to define how an object moves in a scene and how it interacts with other objects.
  
 #  [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Colliders.markdown)
Colliders define the shape of an object. This tells the PhysicsEngine how to compute collisions and, in conjunction with RigidBody, how to resolve them.

 #  [Collision Overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/CollisionOverview.markdown)
A high-level overview of the rules that physics uses to detect and resolve collisions.
  
 #  [PhysicsEffects and Regions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsEffectsAndRegions.markdown)
Effects contain pre-defined methods of applying forces to objects. These effects can be applied per object, per region, and even per space.
  
 #  [Casting](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsCasting.markdown)
Casting allows custom user queries to check for collision in certain regions or directions. This helps facilitate common game-logic queries.

 #  [PhysicsMaterial](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsMaterial.markdown)
PhysicsMaterials describe surface properties for a Collider such as density and restitution.
  
 #  [MassOverride](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/MassOverride.markdown)
Override or take a screenshot of an objects mass.

 #  [Joints](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Joints.markdown)
Joints are an advanced topic to define constrained movement of objects. This can range from simple movement restrictions to defining larger articulate bodies.

 #  [Hierarchies](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Hierarchies.markdown)
Complicated physics objects can be built from how hierarchies are arranged with Colliders and RigidBodies.
  
 #  [Troubleshooting](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsTroubleshooting.markdown)
Common issues the user might run into when working with physics.

 #  [PhysicsSolverConfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSolverConfig.markdown)
The PhysicsSolverConfig resource allows customization of constraint solving (advanced). 

 