 `Component` `UiWidget`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Render](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#render-void)|[ DebugMouseInteraction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#debugmouseinteraction-ze)|[uiwidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uiwidget.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#uirootwidget-void)|[ DebugSelected](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#debugselected-zero-engin)| | |
|[ Update](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#update-void)|[ DepthSeparation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#depthseparation-zero-eng)| | |
| |[ DoubleClickTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#doubleclicktime-zero-eng)| | |
| |[ FocusWidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#focuswidget-zero-engine)| | |
| |[ MouseDownWidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#mousedownwidget-zero-eng)| | |
| |[ MouseHoldTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#mouseholdtime-zero-engin)| | |
| |[ MouseHoverTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#mousehovertime-zero-engi)| | |
| |[ MouseOverWidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uirootwidget.markdown#mouseoverwidget-zero-eng)| | |


 #  Properties


---  
 #  DebugMouseInteraction : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to print out debug information to the console about what the mouse is currently doing.
> ``` lang=cpp, name=Zilch
> var DebugMouseInteraction : Boolean


---  
 #  DebugSelected : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> 
> ``` lang=cpp, name=Zilch
> var DebugSelected : Cog


---  
 #  DepthSeparation : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Used for debugging.
> ``` lang=cpp, name=Zilch
> var DepthSeparation : Real


---  
 #  DoubleClickTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The amount of time between clicks to send the 'DoubleClick' event.
> ``` lang=cpp, name=Zilch
> var DoubleClickTime : Real


---  
 #  FocusWidget : [uiwidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uiwidget.markdown)

> The widget that currently has focus.
> ``` lang=cpp, name=Zilch
> var FocusWidget : UiWidget


---  
 #  MouseDownWidget : [uiwidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uiwidget.markdown)

 `read-only`

> The widget that the mouse was pressed down on.
> ``` lang=cpp, name=Zilch
> var MouseDownWidget : UiWidget


---  
 #  MouseHoldTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Only send the 'MouseHold' event when the mouse has been holding on a single widget for this amount of time.
> ``` lang=cpp, name=Zilch
> var MouseHoldTime : Real


---  
 #  MouseHoverTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Only send the MouseHover event when the mouse has been over a single widget for this amount of time.
> ``` lang=cpp, name=Zilch
> var MouseHoverTime : Real


---  
 #  MouseOverWidget : [uiwidget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/uiwidget.markdown)

 `read-only`

> The widget that the mouse is currently over.
> ``` lang=cpp, name=Zilch
> var MouseOverWidget : UiWidget


---  
 #  Methods


---  
 #  Render : Void

> Renders the Ui to the given color render target. The depth render target must have stencil.
> |Name|Type|Description|
> |---|---|---|
> |e|[rendertasksevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown)| |
> |color|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depth|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |renderPass|[materialblock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function Render(e : RenderTasksEvent, color : RenderTarget, depth : RenderTarget, renderPass : MaterialBlock)
> ``` 


---  
 #  UiRootWidget : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function UiRootWidget()
> ``` 


---  
 #  Update : Void

> Updates all widgets and layouts that need to be updated. This should be called right before rendering.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Update()
> ``` 


---  
 

 