 `Component` `Editor`



(NOTE) A component used for drawing a grid.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#griddraw-void)|[ Active](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#active-zero-engine-docum)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
| |[ AlwaysDrawInEditor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#alwaysdrawineditor-zero)| | |
| |[ Axis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#axis-zero-engine-documen)| | |
| |[ CellSize](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#cellsize-zero-engine-doc)| | |
| |[ DrawAxisOrigins](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#drawaxisorigins-zero-eng)| | |
| |[ DrawInGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#drawingame-zero-engine-d)| | |
| |[ FollowEditorCamera](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#followeditorcamera-zero)| | |
| |[ GridColor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#gridcolor-zero-engine-do)| | |
| |[ GridHighlight](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#gridhighlight-zero-engin)| | |
| |[ HalfCellOffset](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#halfcelloffset-zero-engi)| | |
| |[ HighlightInterval](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#highlightinterval-zero-e)| | |
| |[ Lines](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/griddraw.markdown#lines-zero-engine-docume)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  AlwaysDrawInEditor : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Always draw the grid in editor (not just when it's selected)
> ``` lang=cpp, name=Zilch
> var AlwaysDrawInEditor : Boolean


---  
 #  Axis : [AxisDirection](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#axisdirection)

> 
> ``` lang=cpp, name=Zilch
> var Axis : AxisDirection


---  
 #  CellSize : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The deltas in the grid (how far apart we draw grid lines)
> ``` lang=cpp, name=Zilch
> var CellSize : Real


---  
 #  DrawAxisOrigins : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Changes the line color to.
> ``` lang=cpp, name=Zilch
> var DrawAxisOrigins : Boolean


---  
 #  DrawInGame : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Draw the grid in the game.
> ``` lang=cpp, name=Zilch
> var DrawInGame : Boolean


---  
 #  FollowEditorCamera : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Move with the editor camera?
> ``` lang=cpp, name=Zilch
> var FollowEditorCamera : Boolean


---  
 #  GridColor : [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown)

> Color of grid lines.
> ``` lang=cpp, name=Zilch
> var GridColor : Real4


---  
 #  GridHighlight : [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown)

> 
> ``` lang=cpp, name=Zilch
> var GridHighlight : Real4


---  
 #  HalfCellOffset : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is the grid offset by half a unit?
> ``` lang=cpp, name=Zilch
> var HalfCellOffset : Boolean


---  
 #  HighlightInterval : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> How often should cells be activated.
> ``` lang=cpp, name=Zilch
> var HighlightInterval : Integer


---  
 #  Lines : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> The number of lines to draw.
> ``` lang=cpp, name=Zilch
> var Lines : Integer


---  
 #  Methods


---  
 #  GridDraw : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GridDraw()
> ``` 


---  
 
  
  
  
  
  
  
  

 