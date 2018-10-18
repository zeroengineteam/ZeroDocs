 `Engine`

(NOTE) Game pad is a object for getting game pad input.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ IsButtonHeld](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#isbuttonheld-zero-engine)|[ GamepadIndex](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#gamepadindex-zero-engine)|[eventobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/eventobject.markdown)| |
|[ IsButtonPressed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#isbuttonpressed-zero-eng)|[ IsActive](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#isactive-zero-engine-doc)| | |
|[ IsButtonReleased](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#isbuttonreleased-zero-en)|[ LeftStick](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#leftstick-zero-engine-do)| | |
|[ TimeButtonHeld](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#timebuttonheld-zero-engi)|[ LeftStickDelta](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#leftstickdelta-zero-engi)| | |
|[ Vibrate](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#vibrate-void)|[ LeftTrigger](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#lefttrigger-zero-engine)| | |
| |[ RightStick](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#rightstick-zero-engine-d)| | |
| |[ RightStickDelta](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#rightstickdelta-zero-eng)| | |
| |[ RightTrigger](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown#righttrigger-zero-engine)| | |


 #  Properties


---  
 #  GamepadIndex : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

> Index of this gamepad.
> ``` lang=cpp, name=Zilch
> var GamepadIndex : Integer


---  
 #  IsActive : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Is this controller turned on and plugged in.
> ``` lang=cpp, name=Zilch
> var IsActive : Boolean


---  
 #  LeftStick : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Current offset [-1,1] from the center of the left stick.
> ``` lang=cpp, name=Zilch
> var LeftStick : Real2


---  
 #  LeftStickDelta : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Change in the left stick this frame.
> ``` lang=cpp, name=Zilch
> var LeftStickDelta : Real2


---  
 #  LeftTrigger : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Value of how much the Left Trigger is down. Range [0,1].
> ``` lang=cpp, name=Zilch
> var LeftTrigger : Real


---  
 #  RightStick : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Current offset [-1,1] from the center of the right stick.
> ``` lang=cpp, name=Zilch
> var RightStick : Real2


---  
 #  RightStickDelta : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Change in the right stick this frame.
> ``` lang=cpp, name=Zilch
> var RightStickDelta : Real2


---  
 #  RightTrigger : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Value of how much the Right Trigger is down. Range [0,1].
> ``` lang=cpp, name=Zilch
> var RightTrigger : Real


---  
 #  Methods


---  
 #  IsButtonHeld : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Is the button currently being held down.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsButtonHeld(index : Integer) : Boolean
> ``` 


---  
 #  IsButtonPressed : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Has the button just been pressed this frame.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsButtonPressed(index : Integer) : Boolean
> ``` 


---  
 #  IsButtonReleased : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Is the button just been released.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsButtonReleased(index : Integer) : Boolean
> ``` 


---  
 #  TimeButtonHeld : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How long has this button been held down.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function TimeButtonHeld(index : Integer) : Real
> ``` 


---  
 #  Vibrate : Void

> Vibrate this controller for a given time. Speed is a value between zero and one.
> |Name|Type|Description|
> |---|---|---|
> |time|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |LeftSpeed|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |RightSpeed|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Vibrate(time : Real, LeftSpeed : Real, RightSpeed : Real)
> ``` 


---  
 

 