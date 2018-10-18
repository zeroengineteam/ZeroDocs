A common issue during development is to have two objects not collide when the user thinks they should. To help aid debugging this, [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/physicsspace.markdown) exposes the `WhyAreTheyNotColliding` function. This function takes a pair of objects and returns a string signifying why the physics space doesn't think they're colliding. Here's a short list of a few common reasons:
 - **There isn't a collision**: The objects might just not be colliding. This is often the case when making a 2D game and the objects are on different z-layers. Try to look at the property grid or change the camera angle to verify this.
 - **The collider is static:** See the [Collision Overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/collisionoverview.markdown) page for what goes through collision detection and collision resolution.
 - **No messages are sent:** Ensure that the Collider's SendsEvent checkBox property is true and that a [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/collisionoverview/collisiongroupsandtables.markdown) is not interfering with these events. Additionally, if using the SweptController make sure:
    - [CustomCollisionEventTracker](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customcollisioneventtracker.markdown) component is attached to the same object as the SweptController
    - SweptController's ForwardEvents checkBox property is set to true
 - **The listener didn't connect to the event:** Make sure that the object that is supposed to get a collision event actually connected to the event.
 - **The listener connected incorrectly:** There's two common scenarios for this.
   - 1. Make sure that the correct event type was connected to.
   - 2. Make sure that the listener connected to the right object. Was this the correct cog? Should this have been the PhysicsSpace?

---
 #  Related Materials
 ##  Manual
- [physicstroubleshooting.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting.markdown)
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/colliders.markdown)
- [collisionoverview.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/collisionoverview.markdown)
- [collisiongroupsandtables.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/collisionoverview/collisiongroupsandtables.markdown)

 ##  Reference
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
- [CustomCollisionEventTracker](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customcollisioneventtracker.markdown)
- [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown)
- [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown) 

 