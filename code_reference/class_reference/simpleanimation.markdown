 `Component` `Engine`



(NOTE) Plays a single animation on Initialize.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ChainAnimation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#chainanimation-zero-engi)|[ Animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#animation-zero-engine-do)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ CrossBlend](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#crossblend-zero-engine-d)|[ PlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#playmode-zero-engine-doc)| | |
|[ DirectBlend](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#directblend-zero-engine)| | | |
|[ PlayIsolatedAnimation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#playisolatedanimation-ze)| | | |
|[ PlaySingle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#playsingle-zero-engine-d)| | | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simpleanimation.markdown#simpleanimation-void)| | | |


 #  Properties


---  
 #  Animation : [animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)

> Animation getter/setter.
> ``` lang=cpp, name=Zilch
> var Animation : Animation


---  
 #  PlayMode : [AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)

> Play mode getter/setter.
> ``` lang=cpp, name=Zilch
> var PlayMode : AnimationPlayMode


---  
 #  Methods


---  
 #  ChainAnimation : [animationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animationnode.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |animation|[animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)| |
> |playMode|[AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)| |
> ``` lang=cpp, name=Zilch
> function ChainAnimation(animation : Animation, playMode : AnimationPlayMode) : AnimationNode
> ``` 


---  
 #  CrossBlend : [animationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animationnode.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |animation|[animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)| |
> |transitionTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |playMode|[AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)| |
> ``` lang=cpp, name=Zilch
> function CrossBlend(animation : Animation, transitionTime : Real, playMode : AnimationPlayMode) : AnimationNode
> ``` 


---  
 #  DirectBlend : [animationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animationnode.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |animation|[animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)| |
> |transitionTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |playMode|[AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)| |
> ``` lang=cpp, name=Zilch
> function DirectBlend(animation : Animation, transitionTime : Real, playMode : AnimationPlayMode) : AnimationNode
> ``` 


---  
 #  PlayIsolatedAnimation : [animationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animationnode.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |animation|[animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)| |
> |rootBone|[cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)| |
> |playMode|[AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)| |
> ``` lang=cpp, name=Zilch
> function PlayIsolatedAnimation(animation : Animation, rootBone : Cog, playMode : AnimationPlayMode) : AnimationNode
> ``` 


---  
 #  PlaySingle : [animationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animationnode.markdown)

> Play animations directly.
> |Name|Type|Description|
> |---|---|---|
> |animation|[animation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/animation.markdown)| |
> |playMode|[AnimationPlayMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#animationplaymode)| |
> ``` lang=cpp, name=Zilch
> function PlaySingle(animation : Animation, playMode : AnimationPlayMode) : AnimationNode
> ``` 


---  
 #  SimpleAnimation : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SimpleAnimation()
> ``` 


---  
 

 