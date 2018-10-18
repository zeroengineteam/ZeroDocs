 `Engine`

(NOTE) Mouse object for Display System.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ IsButtonDown](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#isbuttondown-zero-engine)|[ ClientPosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#clientposition-zero-engi)|[eventobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventobject.markdown)| |
|[ ToggleTrapped](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#toggletrapped-void)|[ Cursor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#cursor-zero-engine-docum)| | |
| |[ CursorMovement](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#cursormovement-zero-engi)| | |
| |[ RawMovement](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#rawmovement-zero-engine)| | |
| |[ Trapped](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouse.markdown#trapped-zero-engine-docu)| | |


 #  Properties


---  
 #  ClientPosition : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The position of the mouse cursor relative to the application's top-left corner in pixels.
> ``` lang=cpp, name=Zilch
> var ClientPosition : Real2


---  
 #  Cursor : [Cursor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#cursor)

> Set the cursor of the mouse.
> ``` lang=cpp, name=Zilch
> var Cursor : Cursor


---  
 #  CursorMovement : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The movement of the mouse in pixels.
> ``` lang=cpp, name=Zilch
> var CursorMovement : Real2


---  
 #  RawMovement : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

> High precision raw movement of the mouse.
> ``` lang=cpp, name=Zilch
> var RawMovement : Real2


---  
 #  Trapped : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Trap the mouse preventing it from moving.
> ``` lang=cpp, name=Zilch
> var Trapped : Boolean


---  
 #  Methods


---  
 #  IsButtonDown : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is a mouse button currently down?
> |Name|Type|Description|
> |---|---|---|
> |button|[MouseButtons](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#mousebuttons)| |
> ``` lang=cpp, name=Zilch
> function IsButtonDown(button : MouseButtons) : Boolean
> ``` 


---  
 #  ToggleTrapped : Void

> Toggles if the mouse is currently trapped.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ToggleTrapped()
> ``` 


---  
 

 