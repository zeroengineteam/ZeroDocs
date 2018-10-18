 `Component` `Graphics`



(NOTE) Text that is rendered from a texture atlas in the same way that Sprites are.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetCharacterPosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#getcharacterposition-zer)|[ Font](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#font-zero-engine-documen)|[basesprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/basesprite.markdown)| |
|[ MeasureGivenText](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#measuregiventext-zero-en)|[ FontSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#fontsize-zero-engine-doc)| | |
|[ MeasureText](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#measuretext-zero-engine)|[ PixelsPerUnit](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#pixelsperunit-zero-engin)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#spritetext-void)|[ Text](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#text-zero-engine-documen)| | |
| |[ TextAlign](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritetext.markdown#textalign-zero-engine-do)| | |


 #  Properties


---  
 #  Font : [font](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/font.markdown)

> Font used to display the text.
> ``` lang=cpp, name=Zilch
> var Font : Font


---  
 #  FontSize : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> Size that the font will be rastered at to a texture atlas.
> ``` lang=cpp, name=Zilch
> var FontSize : Integer


---  
 #  PixelsPerUnit : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Number of pixels of the font size that map to one world space unit.
> ``` lang=cpp, name=Zilch
> var PixelsPerUnit : Real


---  
 #  Text : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> Text to display.
> ``` lang=cpp, name=Zilch
> var Text : String


---  
 #  TextAlign : [TextAlign](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textalign)

> How to position the text about the objects origin.
> ``` lang=cpp, name=Zilch
> var TextAlign : TextAlign


---  
 #  Methods


---  
 #  GetCharacterPosition : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Get the position in world space of a character by index.
> |Name|Type|Description|
> |---|---|---|
> |characterIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetCharacterPosition(characterIndex : Integer) : Real3
> ``` 


---  
 #  MeasureGivenText : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

> Get the effective size in world space that the SpriteText would be if this was its text.
> |Name|Type|Description|
> |---|---|---|
> |text|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function MeasureGivenText(text : String) : Real2
> ``` 


---  
 #  MeasureText : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

> Get the effective size in world space of the current text.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function MeasureText() : Real2
> ``` 


---  
 #  SpriteText : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SpriteText()
> ``` 


---  
 

 