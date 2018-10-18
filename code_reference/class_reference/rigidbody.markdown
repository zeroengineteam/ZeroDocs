 `Component` `Physics`



(NOTE) RigidBody defines the inertia (mass, velocity, etc...) of a rigid object. Any PhysicsEffects attached to a RigidBody without a region will be applied to the center of mass of this body.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ApplyAngularImpulse](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyangularimpulse-void)|[ ActiveBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#activebody-zero-engine-d)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ ApplyAngularVelocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyangularvelocity-voi)|[ AllowSleep](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#allowsleep-zero-engine-d)| | |
|[ ApplyForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforce-void)|[ AngularVelocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#angularvelocity-zero-eng)| | |
|[ ApplyForceAtOffsetVector](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforceatoffsetvector)|[ Asleep](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#asleep-zero-engine-docum)| | |
|[ ApplyForceAtOffsetVectorNoWakeUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforceatoffsetvector)|[ DynamicState](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#dynamicstate-zero-engine)| | |
|[ ApplyForceAtPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforceatpoint-void)|[ Force](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#force-zero-engine-docume)| | |
|[ ApplyForceAtPointNoWakeUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforceatpointnowakeu)|[ LocalInverseInertiaTensor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#localinverseinertiatenso)| | |
|[ ApplyForceNoWakeUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyforcenowakeup-void)|[ Mass](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#mass-zero-engine-documen)| | |
|[ ApplyImpulseAtOffsetVector](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyimpulseatoffsetvect)|[ Mode2D](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#mode2d-zero-engine-docum)| | |
|[ ApplyImpulseAtPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyimpulseatpoint-void)|[ RotationLocked](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#rotationlocked-zero-engi)| | |
|[ ApplyLinearImpulse](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applylinearimpulse-void)|[ Torque](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#torque-zero-engine-docum)| | |
|[ ApplyLinearVelocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applylinearvelocity-void)|[ Velocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#velocity-zero-engine-doc)| | |
|[ ApplyTorque](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applytorque-void)|[ WorldCenterOfMass](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#worldcenterofmass-zero-e)| | |
|[ ApplyTorqueNoWakeUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applytorquenowakeup-void)|[ WorldInverseInertiaTensor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#worldinverseinertiatenso)| | |
|[ ApplyVelocityAtPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#applyvelocityatpoint-voi)| | | |
|[ ForceAsleep](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#forceasleep-void)| | | |
|[ ForceAwake](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#forceawake-void)| | | |
|[ GetPointVelocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#getpointvelocity-zero-en)| | | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#rigidbody-void)| | | |


 #  Properties


---  
 #  ActiveBody : [rigidbody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)

 `read-only`

> If this is a static body then the active body (the one force/velocity should be applied to or calculated from) is the nearest parent body up the hierarchy that is not static. If one isn't found then this returns the current rigid body (this).
> ``` lang=cpp, name=Zilch
> var ActiveBody : RigidBody


---  
 #  AllowSleep : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Sleeping happens when an object has not "moved" (small enough linear + angular velocity) for long enough. If this happens then the physics engine stops updating this object (integration, collision detection, etc...) until an awake object hits it. Sleeping is purely an optimization. Sometimes it is not desirable for a body to ever fall asleep (such as a player).
> ``` lang=cpp, name=Zilch
> var AllowSleep : Boolean


---  
 #  AngularVelocity : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The angular velocity (radians per second) of this body in world space. Objects will rotate about this axis using the right-hand rule. Max bounds are around 1e+10, after this the angular velocity will be capped. Setting this will wake up the body if it's asleep.
> ``` lang=cpp, name=Zilch
> var AngularVelocity : Real3


---  
 #  Asleep : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not this object is currently asleep. Setting this to true will force the object asleep even if this causes invalid behavior (objects floating).
> ``` lang=cpp, name=Zilch
> var Asleep : Boolean


---  
 #  DynamicState : [RigidBodyDynamicState](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#rigidbodydynamicstate)

> How this rigid body handles dynamics. Is it a regular rigid body (dynamic)? Does it not move (static)? Does the user want to manually move it and have objects properly collide with it (kinematic)? Note: Static vs. static does not check for collision.
> ``` lang=cpp, name=Zilch
> var DynamicState : RigidBodyDynamicState


---  
 #  Force : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The total accumulated force (in world space) that is being applied to the center of mass of this rigid body this frame. Setting this will wake up the body if it's asleep.
> ``` lang=cpp, name=Zilch
> var Force : Real3


---  
 #  LocalInverseInertiaTensor : [real3x3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x3.markdown)

 `read-only`

> The inverse inertia tensor in local space of this body. The local space inertia tensor doesn't change when the object rotates but is not typically useful for any calculations other than computing the world-space inverse inertia tensor.
> ``` lang=cpp, name=Zilch
> var LocalInverseInertiaTensor : Real3x3


---  
 #  Mass : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The current mass of the rigid body. This includes all child colliders belonging to this body.
> ``` lang=cpp, name=Zilch
> var Mass : Real


---  
 #  Mode2D : [Mode2DStates](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#mode2dstates)

> Used to make an object act as if it were 2D. This is done by locking it to the current z-plane and only allowing rotation about the world's z-axis. Objects can be set to always be 2D or 3D, or this can be deferred to the PhysicsSpace's Mode2D.
> ``` lang=cpp, name=Zilch
> var Mode2D : Mode2DStates


---  
 #  RotationLocked : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Makes physics unable to rotate this object. Manual rotations can still be applied.
> ``` lang=cpp, name=Zilch
> var RotationLocked : Boolean


---  
 #  Torque : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The total accumulated torque (in world space) that is being applied to the center of mass of this rigid body this frame. Setting this will wake up the body if it's asleep.
> ``` lang=cpp, name=Zilch
> var Torque : Real3


---  
 #  Velocity : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The velocity (units per second) of this body in world space. Max bounds are around 1e+10, after this the velocity will be capped. Setting this will wake up the body if it's asleep.
> ``` lang=cpp, name=Zilch
> var Velocity : Real3


---  
 #  WorldCenterOfMass : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The position of the center of mass in world space.
> ``` lang=cpp, name=Zilch
> var WorldCenterOfMass : Real3


---  
 #  WorldInverseInertiaTensor : [real3x3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x3.markdown)

 `read-only`

> The inverse inertia tensor in world space of this body. Describes how hard it is to rotate an object about the world-space axes. Useful to convert any torque into an angular velocity.
> ``` lang=cpp, name=Zilch
> var WorldInverseInertiaTensor : Real3x3


---  
 #  Methods


---  
 #  ApplyAngularImpulse : Void

> Applies an angular impulse through the center of mass (world space). Only results in a change of angular velocity. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |angular|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyAngularImpulse(angular : Real3)
> ``` 


---  
 #  ApplyAngularVelocity : Void

> Adds to the current angular velocity (world space). Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |angular|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyAngularVelocity(angular : Real3)
> ``` 


---  
 #  ApplyForce : Void

> Applies a force through the center of mass of the body (world space). Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForce(force : Real3)
> ``` 


---  
 #  ApplyForceAtOffsetVector : Void

> Applies a force at an offset from the center of mass (world space). Results in a force and torque to the center of mass. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldOffset|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForceAtOffsetVector(force : Real3, worldOffset : Real3)
> ``` 


---  
 #  ApplyForceAtOffsetVectorNoWakeUp : Void

> Applies a force at an offset from the center of mass (world space). Results in a force and torque to the center of mass. Will not wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldOffset|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForceAtOffsetVectorNoWakeUp(force : Real3, worldOffset : Real3)
> ``` 


---  
 #  ApplyForceAtPoint : Void

> Applies a force at a world point (world space). Results in a force and torque to the center of mass. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForceAtPoint(force : Real3, worldPoint : Real3)
> ``` 


---  
 #  ApplyForceAtPointNoWakeUp : Void

> Applies a force at a world point (world space). Results in a force and torque to the center of mass. Will not wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForceAtPointNoWakeUp(force : Real3, worldPoint : Real3)
> ``` 


---  
 #  ApplyForceNoWakeUp : Void

> Applies a force through the center of mass of the body (world space). Will not wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |force|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyForceNoWakeUp(force : Real3)
> ``` 


---  
 #  ApplyImpulseAtOffsetVector : Void

> Applies an impulse at on offset from the center of mass (world space). Results in a change in linear and angular velocity. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |impulse|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldOffset|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyImpulseAtOffsetVector(impulse : Real3, worldOffset : Real3)
> ``` 


---  
 #  ApplyImpulseAtPoint : Void

> Applies an impulse at a world point (world space). Results in a change to linear and angular velocity. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |impulse|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyImpulseAtPoint(impulse : Real3, worldPoint : Real3)
> ``` 


---  
 #  ApplyLinearImpulse : Void

> Applies a linear impulse through the center of mass (world space). Only results in a change of linear velocity. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |linear|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyLinearImpulse(linear : Real3)
> ``` 


---  
 #  ApplyLinearVelocity : Void

> Adds to the current linear velocity (world space). Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |linear|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyLinearVelocity(linear : Real3)
> ``` 


---  
 #  ApplyTorque : Void

> Applies a torque through the center of mass of the body (world space). Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |torque|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyTorque(torque : Real3)
> ``` 


---  
 #  ApplyTorqueNoWakeUp : Void

> Applies a torque through the center of mass of the body (world space). Will not wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |torque|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyTorqueNoWakeUp(torque : Real3)
> ``` 


---  
 #  ApplyVelocityAtPoint : Void

> Applies a velocity at a world space point on the object. Results in a change to linear and angular velocity. Will wake up the body if it's asleep.
> |Name|Type|Description|
> |---|---|---|
> |velocity|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ApplyVelocityAtPoint(velocity : Real3, worldPoint : Real3)
> ``` 


---  
 #  ForceAsleep : Void

> Forces the object asleep. Warning: calling this function could create gameplay flaws if used incorrectly, use at your own risk (and sparingly).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ForceAsleep()
> ``` 


---  
 #  ForceAwake : Void

> Forces the object awake. Will reset the sleep timer.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ForceAwake()
> ``` 


---  
 #  GetPointVelocity : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> Computes the linear point velocity of world-space point.
> |Name|Type|Description|
> |---|---|---|
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetPointVelocity(worldPoint : Real3) : Real3
> ``` 


---  
 #  RigidBody : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RigidBody()
> ``` 


---  
 

 