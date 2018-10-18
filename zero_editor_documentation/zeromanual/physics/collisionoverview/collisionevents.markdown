[ CollisionEvents](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CollisionEvent.markdown) are the primary way that physics sends collision information to users. Three main event types are sent out for collisions: starting, persisting, and ending.

Collision events are often used in gameplay, such as applying damage if an impact was large enough. Sometimes it is necessary to alter information about the two objects involved in a collision, such as their velocity. Other common examples include creating audio effects or graphics effects in response to a collision, such as a scraping sound and sparks of a sliding metal object.

 #  Collision Event Types
There are three primary collision events sent out. These events are typically sent to both objects involved and to the [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsSpace.markdown). If you're having trouble receiving events then see [WhyAreTheyNotColliding](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/physicstroubleshooting/whyaretheynotcolliding.markdown).

- **CollisionStarted** is sent out on the first frame two objects come into contact.
- **CollisionPersisted** is sent every frame two objects are in contact. This event is not sent on the first frame of collision.
- **CollisionEnded** is sent the frame that contact is broken. At this point the two objects are no longer in contact. This event is also sent if an object is destroyed.

 #  CollisionEvents Order
The physics system will send out all CollisionEvents after resolving all collisions in the space. This means that some of the information in the event is //old//. This is most obvious when inspecting an object's position and velocity as both will reflect the post-collision resolution information. This is necessary to give final collision information like the final applied impulse. If pre-collision resolution information is desired, see [PreSolveEvent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PreSolveEvent.markdown) of [CollisionTables](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/collisiongroupsandtables.markdown).

 #  Properties
There's a few properties worth discussing in detail on CollisionEvents.

 ##  Object vs. OtherObject
A collision event is sent with one object as the focus; that is to say that most information will have a primary object and a secondary object. This is necessary to know what direction other properties, such as the collision normal, face. If the event is received from the physics space then this ordering is not defined.

 ##  ContactPoints
A CollisionEvent exposes a range of contact points. For physics to solve a collision, several points of contact may be necessary. Often in game logic, one contact point is sufficient; for convenience, the FirstPoint  property is exposed. [ ContactPoints](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ContactPoint.markdown) expose information about what happened in a collision:

**Local and World Points:** Contact points expose both a local and world space point on each object.

**Contact Normal:** The normal of a collision describes the primary direction that collision is resolved in. ContactPoint exposes WorldNormalTowardsOther  which is the normal from the WorldPoint on *this// object towards the //other// object. This can be useful for pushing the //other// object away from //this//. To get the world normal towards //this* object just negate this property.

**Impulses:** The physics system solves collisions with impulses, i.e. an instantaneous force. To properly solve a collision there are three values: the normal impulse and two friction impulses. 

The normal impulse is the scalar impulse value that is applied in the direction of the contact normal to resolve the collision. This can be used to measure the strength of an impact between the two objects. Keep in mind that an impulse contains the inverse mass sum of the two objects involved.

The two friction impulses are applied in tangential directions to the normal impulse to slow down an object. ContactPoint exposes FrictionImpulse , which is the total friction magnitude that was applied. Additionally, ComplexImpulse  is exposed, which contains the normal, friction1, and friction2 values in the x, y, and z components of the vector respectively.

---
 # Related Materials
 ##  Manual
- [WhyAreTheyNotColliding.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsTroubleshooting/WhyAreTheyNotColliding.markdown)
- [PhysicsSpace.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsSpace.markdown)
- [CollisionGroupsAndTables.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/CollisionGroupsAndTables.markdown)
 ##  Reference
- [CollisionEvent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CollisionEvent.markdown)
- [ContactPoint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ContactPoint.markdown)
- [PreSolveEvent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PreSolveEvent.markdown)
- [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown) 
  
  
  
  
  
  
  

 