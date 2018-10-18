 `Component` `Physics`



(NOTE) Defines spring properties for a joint. Used to make a joint soft and therefore behave spring-like. A joint spring has a frequency in hertz at which to oscillate as well as a damping ratio. The ratio should vary from 0 to 1 where 0 is no damping and 1 is critical damping. See each joint for a description of how it reacts to a spring.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/jointspring.markdown#jointspring-void)|[ Active](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/jointspring.markdown#active-zero-engine-docum)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
| |[ AtomIds](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/jointspring.markdown#atomids-zero-engine-docu)| | |
| |[ DampingRatio](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/jointspring.markdown#dampingratio-zero-engine)| | |
| |[ FrequencyHz](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/jointspring.markdown#frequencyhz-zero-engine)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Determines if this spring is active.
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  AtomIds : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Signifies what atoms on the joint this affects. For internal use.
> ``` lang=cpp, name=Zilch
> var AtomIds : Integer


---  
 #  DampingRatio : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The damping ratio of this spring. The value should range from 0 to 1 where 0 is no damping and 1 is critical damping.
> ``` lang=cpp, name=Zilch
> var DampingRatio : Real


---  
 #  FrequencyHz : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The oscillation frequency of the spring in Hertz (cycles per second).
> ``` lang=cpp, name=Zilch
> var FrequencyHz : Real


---  
 #  Methods


---  
 #  JointSpring : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function JointSpring()
> ``` 


---  
 
  
  
  
  
  
  
  

 