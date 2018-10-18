 `Component` `Physics`



(NOTE) Allows the user to override parameters for debug drawing of joints. Primarily used to debug draw from different object perspectives and to change the size of drawn data.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#jointdebugdrawconfig-voi)|[ Active](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#active-zero-engine-docum)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
| |[ Detail](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#detail-zero-engine-docum)| | |
| |[ ObjectAPerspective](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#objectaperspective-zero)| | |
| |[ ObjectBPerspective](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#objectbperspective-zero)| | |
| |[ Size](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointdebugdrawconfig.markdown#size-zero-engine-documen)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not this component is active.
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  Detail : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The amount of detail to use when drawing. For example, the detail on a RevoluteJoint will increase the number of lines used to draw the arc of a circle.
> ``` lang=cpp, name=Zilch
> var Detail : Real


---  
 #  ObjectAPerspective : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If we draw the joint's debug info from the perspective of ObjectA. Typically used when ObjectA is marked as a static object and ObjectB has free movement.
> ``` lang=cpp, name=Zilch
> var ObjectAPerspective : Boolean


---  
 #  ObjectBPerspective : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If we draw the joint's debug info from the perspective of ObjectB. Typically used when ObjectB is marked as a static object and ObjectA has free movement.
> ``` lang=cpp, name=Zilch
> var ObjectBPerspective : Boolean


---  
 #  Size : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> A size modifier for the debug drawing. 1 is the base size.
> ``` lang=cpp, name=Zilch
> var Size : Real


---  
 #  Methods


---  
 #  JointDebugDrawConfig : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function JointDebugDrawConfig()
> ``` 


---  
 

 