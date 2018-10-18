 `Component` `Physics`



(NOTE) Takes a snap shot of the current mass and inertia and overrides the object's mass so it can be resized while keeping it's old mass.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#massoverride-void)|[ Active](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#active-zero-engine-docum)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
|[ RecomputeMass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#recomputemass-void)|[ AutoComputeCenterOfMass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#autocomputecenterofmass)| | |
| |[ AutoComputeInertia](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#autocomputeinertia-zero)| | |
| |[ InverseMass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#inversemass-zero-engine)| | |
| |[ LocalCenterOfMass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#localcenterofmass-zero-e)| | |
| |[ LocalInverseInertiaTensor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#localinverseinertiatenso)| | |
| |[ Mass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/massoverride.markdown#mass-zero-engine-documen)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Determines whether the RigidBody on this Cog will use the cached or actual mass and inertia.
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  AutoComputeCenterOfMass : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Should the center of mass be auto computed or overwritten (via script).
> ``` lang=cpp, name=Zilch
> var AutoComputeCenterOfMass : Boolean


---  
 #  AutoComputeInertia : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Should the inertia tensor be auto computed or overwritten (via script).
> ``` lang=cpp, name=Zilch
> var AutoComputeInertia : Boolean


---  
 #  InverseMass : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The cached inverse mass of this object.
> ``` lang=cpp, name=Zilch
> var InverseMass : Real


---  
 #  LocalCenterOfMass : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> The center of mass in local space to override with. When set, the center of mass will be locked to this value until AutoComputeCenterOfMass is set to true.
> ``` lang=cpp, name=Zilch
> var LocalCenterOfMass : Real3


---  
 #  LocalInverseInertiaTensor : [real3x3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3x3.markdown)

> The inverse inertia tensor this object is saved with.
> ``` lang=cpp, name=Zilch
> var LocalInverseInertiaTensor : Real3x3


---  
 #  Mass : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Overrides the mass of this body. Inertia is updated as a ratio of the new mass to the old mass.
> ``` lang=cpp, name=Zilch
> var Mass : Real


---  
 #  Methods


---  
 #  MassOverride : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function MassOverride()
> ``` 


---  
 #  RecomputeMass : Void

> Takes a new snapshot of the current mass and inertia.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RecomputeMass()
> ``` 


---  
 
  
  
  
  
  
  
  

 