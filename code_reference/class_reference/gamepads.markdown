 `Engine`

(NOTE) Gamepads is a collection of gamepads.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetGamePad](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepads.markdown#getgamepad-zero-engine-d)|[ MaxGamepadCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepads.markdown#maxgamepadcount-zero-eng)|[eventobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/eventobject.markdown)| |
|[ PauseVibration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepads.markdown#pausevibration-void)| | | |
|[ ResumeVibration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepads.markdown#resumevibration-void)| | | |


 #  Properties


---  
 #  MaxGamepadCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Gets the maximum number of supported gamepads.
> ``` lang=cpp, name=Zilch
> var MaxGamepadCount : Integer


---  
 #  Methods


---  
 #  GetGamePad : [gamepad](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepad.markdown)

> Get the gamepad for a given index from [0, GamepadCount].
> |Name|Type|Description|
> |---|---|---|
> |gamepadIndex|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetGamePad(gamepadIndex : Integer) : Gamepad
> ``` 


---  
 #  PauseVibration : Void

> Pause Vibration on all gamepads.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PauseVibration()
> ``` 


---  
 #  ResumeVibration : Void

> Resume vibration on all gamepads.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ResumeVibration()
> ``` 


---  
 
  
  
  
  
  
  
  

 