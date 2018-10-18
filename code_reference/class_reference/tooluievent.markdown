 `Event` `Editor`



(NOTE) Allows Ui customization for Tools. This will be sent on the Tool every time it is activated.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ NeedsPropertyGrid](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/tooluievent.markdown#needspropertygrid-zero-e)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ Parent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/tooluievent.markdown#parent-zero-engine-docum)| | |
| |[ SelectTool](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/tooluievent.markdown#selecttool-zero-engine-d)| | |


 #  Properties


---  
 #  NeedsPropertyGrid : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to force show the tools window when switched to this tool.
> ``` lang=cpp, name=Zilch
> var NeedsPropertyGrid : Boolean


---  
 #  Parent : [composite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/composite.markdown)

 `read-only`

> Getters / setters.
> ``` lang=cpp, name=Zilch
> var Parent : Composite


---  
 #  SelectTool : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Easy access to the Select Tool. It's commonly used in other Tools (such as ray casting).
> ``` lang=cpp, name=Zilch
> var SelectTool : Cog


---  
 #  Methods


---  
 

 