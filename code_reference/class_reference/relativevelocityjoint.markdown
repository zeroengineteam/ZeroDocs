 `Component` `Physics`



(NOTE) A relative velocity joint defines what the desired relative velocity on three world axes should be between two objects. Relative velocity is defined as v2 - v1. This joint has not been tested with motors or limits in any way.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#getaxis-zero-engine-docu)| |[joint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/joint.markdown)| |
|[ GetAxisActive](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#getaxisactive-zero-engin)| | | |
|[ GetMaxImpulse](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#getmaximpulse-zero-engin)| | | |
|[ GetSpeed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#getspeed-zero-engine-doc)| | | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#relativevelocityjoint-vo)| | | |
|[ SetAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#setaxis-void)| | | |
|[ SetAxisActive](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#setaxisactive-void)| | | |
|[ SetMaxImpulse](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#setmaximpulse-void)| | | |
|[ SetSpeed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/relativevelocityjoint.markdown#setspeed-void)| | | |


 #  Properties


---  
 #  Methods


---  
 #  GetAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> One of 3 axes to constrain movement on.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(index : Integer) : Real3
> ``` 


---  
 #  GetAxisActive : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not the given axis index is active.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxisActive(index : Integer) : Boolean
> ``` 


---  
 #  GetMaxImpulse : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The max impulse for the given axis index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetMaxImpulse(index : Integer) : Real
> ``` 


---  
 #  GetSpeed : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The desired relative speed for the given axis index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetSpeed(index : Integer) : Real
> ``` 


---  
 #  RelativeVelocityJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RelativeVelocityJoint()
> ``` 


---  
 #  SetAxis : Void

> One of 3 axes to constrain movement on.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |axis|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetAxis(index : Integer, axis : Real3)
> ``` 


---  
 #  SetAxisActive : Void

> Whether or not the given axis index is active.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |active|[boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetAxisActive(index : Integer, active : Boolean)
> ``` 


---  
 #  SetMaxImpulse : Void

> The max impulse for the given axis index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |maxImpulse|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetMaxImpulse(index : Integer, maxImpulse : Real)
> ``` 


---  
 #  SetSpeed : Void

> The desired relative speed for the given axis index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |speed|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetSpeed(index : Integer, speed : Real)
> ``` 


---  
 

 