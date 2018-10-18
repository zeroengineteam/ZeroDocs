 `Component` `Physics`



(NOTE) Applies a torque to the center of mass of a body.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/torqueeffect.markdown#torqueeffect-void)|[ LocalTorque](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/torqueeffect.markdown#localtorque-zero-engine)|[physicseffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicseffect.markdown)| |
| |[ TorqueAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/torqueeffect.markdown#torqueaxis-zero-engine-d)| | |
| |[ TorqueStrength](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/torqueeffect.markdown#torquestrength-zero-engi)| | |
| |[ WorldTorqueAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/torqueeffect.markdown#worldtorqueaxis-zero-eng)| | |


 #  Properties


---  
 #  LocalTorque : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Determines if the torque is applied in local or world space.
> ``` lang=cpp, name=Zilch
> var LocalTorque : Boolean


---  
 #  TorqueAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The axis that the torque is being applied about.
> ``` lang=cpp, name=Zilch
> var TorqueAxis : Real3


---  
 #  TorqueStrength : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The strength of the torque being applied.
> ``` lang=cpp, name=Zilch
> var TorqueStrength : Real


---  
 #  WorldTorqueAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The axis of the torque in world space (can be used to manually add torque to a RigidBody).
> ``` lang=cpp, name=Zilch
> var WorldTorqueAxis : Real3


---  
 #  Methods


---  
 #  TorqueEffect : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function TorqueEffect()
> ``` 


---  
 

 