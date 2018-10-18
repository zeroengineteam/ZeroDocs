 `Component` `Physics`



(NOTE) Applies a force to make an object move at a target speed in a given direction. This can also be used to pull the object towards the center of the flow (the axis in the flow direction centered at the effect). Used to model a river or a tractor beam.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#floweffect-void)|[ AttractSpeed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#attractspeed-zero-engine)|[physicseffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicseffect.markdown)| |
| |[ AttractToFlowCenter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#attracttoflowcenter-zero)| | |
| |[ FlowDirection](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#flowdirection-zero-engin)| | |
| |[ FlowSpeed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#flowspeed-zero-engine-do)| | |
| |[ LocalForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#localforce-zero-engine-d)| | |
| |[ MaxAttractForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#maxattractforce-zero-eng)| | |
| |[ MaxFlowForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#maxflowforce-zero-engine)| | |
| |[ WorldFlowDirection](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/floweffect.markdown#worldflowdirection-zero)| | |


 #  Properties


---  
 #  AttractSpeed : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The target speed for an object to be pulled towards the center of the flow.
> ``` lang=cpp, name=Zilch
> var AttractSpeed : Real


---  
 #  AttractToFlowCenter : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Determines if the flow field will attract objects towards the center of the field. This can be used to create a tractor beam effect that will keep the object inside of the flow field.
> ``` lang=cpp, name=Zilch
> var AttractToFlowCenter : Boolean


---  
 #  FlowDirection : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The direction that the field is flowing. This can be defined in world or local space.
> ``` lang=cpp, name=Zilch
> var FlowDirection : Real3


---  
 #  FlowSpeed : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The target speed of objects in the flow field.
> ``` lang=cpp, name=Zilch
> var FlowSpeed : Real


---  
 #  LocalForce : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Determines if the flow direction is in the local space of the object.
> ``` lang=cpp, name=Zilch
> var LocalForce : Boolean


---  
 #  MaxAttractForce : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The max force that can be used to reach the target attract speed.
> ``` lang=cpp, name=Zilch
> var MaxAttractForce : Real


---  
 #  MaxFlowForce : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The max force that can be used to reach the target flow speed.
> ``` lang=cpp, name=Zilch
> var MaxFlowForce : Real


---  
 #  WorldFlowDirection : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The direction that the field is flowing in world space.
> ``` lang=cpp, name=Zilch
> var WorldFlowDirection : Real3


---  
 #  Methods


---  
 #  FlowEffect : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FlowEffect()
> ``` 


---  
 

 