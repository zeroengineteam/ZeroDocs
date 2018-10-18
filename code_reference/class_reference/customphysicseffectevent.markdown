 `Event` `Physics`



(NOTE) Event data for applying custom physics effects.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customphysicseffectevent.markdown#customphysicseffectevent)|[ Dt](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customphysicseffectevent.markdown#dt-zero-engine-documenta)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ Effect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customphysicseffectevent.markdown#effect-zero-engine-docum)| | |
| |[ RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customphysicseffectevent.markdown#rigidbody-zero-engine-do)| | |


 #  Properties


---  
 #  Dt : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The timestep of the current physics frame (in seconds).
> ``` lang=cpp, name=Zilch
> var Dt : Real


---  
 #  Effect : [customphysicseffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customphysicseffect.markdown)

> The effect that sent out this event.
> ``` lang=cpp, name=Zilch
> var Effect : CustomPhysicsEffect


---  
 #  RigidBody : [rigidbody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)

> The RigidBody to apply forces to.
> ``` lang=cpp, name=Zilch
> var RigidBody : RigidBody


---  
 #  Methods


---  
 #  CustomPhysicsEffectEvent : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CustomPhysicsEffectEvent()
> ``` 


---  
 

 