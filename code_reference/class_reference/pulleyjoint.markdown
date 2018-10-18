 `Component` `Physics`



(NOTE) A PulleyJoint turns two StickJoints into a pulley via a pulley ratio. A PulleyJoint connects the two free objects of two different stick joints. These two objects will then be bound to move together via the formula "length0 + ratio * length1 = 0". Limits, motors and springs should not be used on a pulley.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#pulleyjoint-void)|[ JointA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#jointa-zero-engine-docum)|[joint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joint.markdown)| |
| |[ JointAPath](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#jointapath-zero-engine-d)| | |
| |[ JointB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#jointb-zero-engine-docum)| | |
| |[ JointBPath](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#jointbpath-zero-engine-d)| | |
| |[ Ratio](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/pulleyjoint.markdown#ratio-zero-engine-docume)| | |


 #  Properties


---  
 #  JointA : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

> The joint connected to ObjectA that the pulley operates on.
> ``` lang=cpp, name=Zilch
> var JointA : Cog


---  
 #  JointAPath : [cogpath](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cogpath.markdown)

> The joint connected to ObjectA that the pulley operates on.
> ``` lang=cpp, name=Zilch
> var JointAPath : CogPath


---  
 #  JointB : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

> The joint connected to ObjectB that the pulley operates on.
> ``` lang=cpp, name=Zilch
> var JointB : Cog


---  
 #  JointBPath : [cogpath](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cogpath.markdown)

> The joint connected to ObjectB that the pulley operates on.
> ``` lang=cpp, name=Zilch
> var JointBPath : CogPath


---  
 #  Ratio : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The ratio between the two stick joints. The ratio is used in the formula "length0 + ratio * length1 = 0".
> ``` lang=cpp, name=Zilch
> var Ratio : Real


---  
 #  Methods


---  
 #  PulleyJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PulleyJoint()
> ``` 


---  
 
  
  
  
  
  
  
  

 