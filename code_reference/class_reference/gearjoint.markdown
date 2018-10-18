 `Component` `Physics`



(NOTE) A gear connects two joints on two objects together. Either joint can be a prismatic or a revolute. A gear ratio is used to bind the two joints together. Limits, motors, and springs should not be used on this.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#gearjoint-void)|[ Constant](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#constant-zero-engine-doc)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
| |[ JointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#jointa-zero-engine-docum)| | |
| |[ JointAPath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#jointapath-zero-engine-d)| | |
| |[ JointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#jointb-zero-engine-docum)| | |
| |[ JointBPath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#jointbpath-zero-engine-d)| | |
| |[ Ratio](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gearjoint.markdown#ratio-zero-engine-docume)| | |


 #  Properties


---  
 #  Constant : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The initial offset of the gear ratio.
> ``` lang=cpp, name=Zilch
> var Constant : Real


---  
 #  JointA : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> The joint connected to ObjectA that the gear operates on.
> ``` lang=cpp, name=Zilch
> var JointA : Cog


---  
 #  JointAPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cogpath.markdown)

> The joint connected to ObjectA that the gear operates on.
> ``` lang=cpp, name=Zilch
> var JointAPath : CogPath


---  
 #  JointB : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> The joint connected to ObjectB that the gear operates on.
> ``` lang=cpp, name=Zilch
> var JointB : Cog


---  
 #  JointBPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cogpath.markdown)

> The joint connected to ObjectB that the gear operates on.
> ``` lang=cpp, name=Zilch
> var JointBPath : CogPath


---  
 #  Ratio : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The gear ratio that the two constraints are bound with.
> ``` lang=cpp, name=Zilch
> var Ratio : Real


---  
 #  Methods


---  
 #  GearJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GearJoint()
> ``` 


---  
 

 