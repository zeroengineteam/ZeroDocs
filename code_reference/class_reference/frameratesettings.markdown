 `Component` `Engine`



(NOTE) Settings for how the frame rate of the engine should be controlled.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/frameratesettings.markdown#frameratesettings-void)|[ FrameRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/frameratesettings.markdown#framerate-zero-engine-do)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
| |[ LimitFrameRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/frameratesettings.markdown#limitframerate-zero-engi)| | |
| |[ VerticalSync](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/frameratesettings.markdown#verticalsync-zero-engine)| | |


 #  Properties


---  
 #  FrameRate : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> How many frames per second the engine should be limited at.
> ``` lang=cpp, name=Zilch
> var FrameRate : Integer


---  
 #  LimitFrameRate : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If the engine should limit the frame rate.
> ``` lang=cpp, name=Zilch
> var LimitFrameRate : Boolean


---  
 #  VerticalSync : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If the frame rate should sync with the monitor's refresh rate, superseded by LimitFrameRate.
> ``` lang=cpp, name=Zilch
> var VerticalSync : Boolean


---  
 #  Methods


---  
 #  FrameRateSettings : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FrameRateSettings()
> ``` 


---  
 

 