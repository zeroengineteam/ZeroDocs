 `Engine`

(NOTE) A Joystick is associated with a hardware joystick, and provides the ability to query axes and buttons.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Calibrating](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#calibrating-zero-engine)|[ AxisCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#axiscount-zero-engine-do)|[eventobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/eventobject.markdown)| |
|[ EndCalibration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#endcalibration-void)|[ ButtonCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#buttoncount-zero-engine)| | |
|[ GetAxisIndex](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#getaxisindex-zero-engine)|[ DisabledValue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#disabledvalue-zero-engin)| | |
|[ GetAxisName](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#getaxisname-zero-engine)|[ IsActive](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#isactive-zero-engine-doc)| | |
|[ GetAxisValue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#getaxisvalue-zero-engine)|[ Name](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#name-zero-engine-documen)| | |
|[ GetAxisValueByName](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#getaxisvaluebyname-zero)| | | |
|[ GetButtonValue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#getbuttonvalue-zero-engi)| | | |
|[ LoadInputMapping](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#loadinputmapping-void)| | | |
|[ SaveInputMapping](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#saveinputmapping-void)| | | |
|[ StartCalibration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joystick.markdown#startcalibration-void)| | | |


 #  Properties


---  
 #  AxisCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var AxisCount : Integer


---  
 #  ButtonCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Get the number of buttons or axes.
> ``` lang=cpp, name=Zilch
> var ButtonCount : Integer


---  
 #  DisabledValue : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only` `static`

> A value that means a joystick axis is invalid. For example when a HAT-switch is not pressed down, it will return this value.
> ``` lang=cpp, name=Zilch
> var DisabledValue : Real


---  
 #  IsActive : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Gets whether or not the joystick is active.
> ``` lang=cpp, name=Zilch
> var IsActive : Boolean


---  
 #  Name : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> Get the name of the Joystick.
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  Methods


---  
 #  Calibrating : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Calibrating() : Boolean
> ``` 


---  
 #  EndCalibration : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function EndCalibration()
> ``` 


---  
 #  GetAxisIndex : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxisIndex(name : String) : Integer
> ``` 


---  
 #  GetAxisName : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxisName(index : Integer) : String
> ``` 


---  
 #  GetAxisValue : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Queries an axes and returns a value between [-1, 1]. The valid range of axes is between 0 and 'GetMaxAxes'. If the axis is not valid, then the value returned is 0. If the axis is disabled, then the value returned is Joystick.DisabledValue.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxisValue(index : Integer) : Real
> ``` 


---  
 #  GetAxisValueByName : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxisValueByName(name : String) : Real
> ``` 


---  
 #  GetButtonValue : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Queries a button and returns true if it is down, false if it is up The valid range of buttons is between 0 and 'GetMaxButtons' If the button is not valid, then the value returned is false.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetButtonValue(index : Integer) : Boolean
> ``` 


---  
 #  LoadInputMapping : Void

> Load an input mapping.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function LoadInputMapping(name : String)
> ``` 


---  
 #  SaveInputMapping : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function SaveInputMapping(name : String)
> ``` 


---  
 #  StartCalibration : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StartCalibration()
> ``` 


---  
 
  
  
  
  
  
  
  

 