Sometimes when a small object is moving fast it might seem to pass through other objects. This is an artifact in physics engines known as tunneling. Before explaining this, understanding some basic concepts in physics engines is important.

 #  Discrete Collision Detection
Game physics engines are commonly implemented using a discrete collision detection model. In a discrete model, objects teleport from frame-to-frame. One way to view this is as a picture flip-book; in each subsequent picture the object teleports to its new position.



![DiscretePhysics](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46691.gif)

Pictured above is an illustration of discrete physics. Notice how there are gaps in the object's movement trail due to a lowered framerate. Typically a physics engine runs at a much higher framerate which is why motion seems smooth.

 #  Tunneling
As an object becomes smaller and moves faster it becomes more likely to tunnel. Tunneling is when an object misses a collision due to moving too fast.



![Tunneling](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46693.PNG)

In the above picture, the red ball is moving at a constant speed to the right with a framerate of `1` fps. In this example no collision is detected as the ball teleports past the wall without ever coming into contact with it.

Tunneling happens even if the framerate is high. The faster and smaller an object the more likely tunneling is to happen. Additionally, tunneling doesn't just result in collisions being missed. Sometimes tunneling can result in wrong collisions.



![Tunneling2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46695.PNG)


In the above picture the ball does end up hitting the wall; however, it hits on the opposite side. In this way the collision will be detected but in the wrong direction.

 #  Fixing Tunneling
The easiest way to fix tunneling is to limit the size and speed of an object. If an object can't move faster than its "radius" each frame then it won't tunnel.

Another way to avoid tunneling is to increase the framerate of the simulation. [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/PhysicsSpace.markdown) exposes SubStepCount  which allows the user to run physics at a higher framerate.

The final way to avoid tunneling is to use continuous collision detection. Currently, continuous collision detection is only available through PhysicsSpace's `SweepCollider` function  which is meant for character controllers. See the SweptController script for an example. Future plans include making this an option on rigid bodies. 

NOTE: Continuous collision detection is significantly more computationally expensive than discrete.

---
 # Related Materials
 ## Manual
- [physicstroubleshooting.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting.markdown)
- [CollisionOverview.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/CollisionOverview.markdown)
- [PhysicsSpace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicstroubleshooting/PhysicsSpace.markdown)
 ##  Reference
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsSpace.markdown) 

 