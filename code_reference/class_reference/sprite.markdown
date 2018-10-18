 `Component` `Graphics`



(NOTE) A generated quad that addresses atlased image data for efficient frame-based animations and batched rendering.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#sprite-void)|[ AnimationActive](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#animationactive-zero-eng)|[basesprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/basesprite.markdown)| |
| |[ AnimationSpeed](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#animationspeed-zero-engi)| | |
| |[ CurrentFrame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#currentframe-zero-engine)| | |
| |[ FlipX](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#flipx-zero-engine-docume)| | |
| |[ FlipY](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#flipy-zero-engine-docume)| | |
| |[ SpriteSource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#spritesource-zero-engine)| | |
| |[ StartFrame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown#startframe-zero-engine-d)| | |


 #  Properties


---  
 #  AnimationActive : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If the Sprite animation should be playing on logic update, paused if false.
> ``` lang=cpp, name=Zilch
> var AnimationActive : Boolean


---  
 #  AnimationSpeed : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Scalar to the amount of time passed used to advance frames of animation.
> ``` lang=cpp, name=Zilch
> var AnimationSpeed : Real


---  
 #  CurrentFrame : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Index of the frame the animation is currently on.
> ``` lang=cpp, name=Zilch
> var CurrentFrame : Integer


---  
 #  FlipX : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Flips the X axis of the Sprite's image (left/right).
> ``` lang=cpp, name=Zilch
> var FlipX : Boolean


---  
 #  FlipY : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Flips the Y axis of the Sprite's image (top/bottom).
> ``` lang=cpp, name=Zilch
> var FlipY : Boolean


---  
 #  SpriteSource : [spritesource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spritesource.markdown)

> The resource defining one or more image sequences used for frame-based animation.
> ``` lang=cpp, name=Zilch
> var SpriteSource : SpriteSource


---  
 #  StartFrame : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Index of the frame to start the animation on when the object is initialized, 0-based.
> ``` lang=cpp, name=Zilch
> var StartFrame : Integer


---  
 #  Methods


---  
 #  Sprite : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Sprite()
> ``` 


---  
 
  
  
  
  
  
  
  

 