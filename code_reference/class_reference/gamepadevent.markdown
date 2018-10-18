 `Event` `Engine`



(NOTE) Gamepad events are send when a game pad button state is changed.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Button](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepadevent.markdown#button-zero-engine-docum)|[event](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/event.markdown)| |
| |[ FlickDirection](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepadevent.markdown#flickdirection-zero-engi)| | |
| |[ FlickedStick](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepadevent.markdown#flickedstick-zero-engine)| | |
| |[ Gamepad](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepadevent.markdown#gamepad-zero-engine-docu)| | |


 #  Properties


---  
 #  Button : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Button that was just pressed down or released up.
> ``` lang=cpp, name=Zilch
> var Button : Integer


---  
 #  FlickDirection : [real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)

> The direction of the stick that was flicked (normalized)
> ``` lang=cpp, name=Zilch
> var FlickDirection : Real2


---  
 #  FlickedStick : [FlickedStick](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#flickedstick)

> When responding to the 'GamepadStickFlicked' event, this will be set to the stick that was flicked.
> ``` lang=cpp, name=Zilch
> var FlickedStick : FlickedStick


---  
 #  Gamepad : [gamepad](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gamepad.markdown)

> Gamepad that generated this event.
> ``` lang=cpp, name=Zilch
> var Gamepad : Gamepad


---  
 #  Methods


---  
 
  
  
  
  
  
  
  

 