 `Engine`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Clone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#clone-zero-engine-docume)|[ CollapseToPoseOnFinish](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#collapsetoposeonfinish-z)|[referencecountedeventobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/referencecountedeventobject.markdown)|[basicanimation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/basicanimation.markdown)|
|[ CollapseToPose](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#collapsetopose-void)|[ Duration](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#duration-zero-engine-doc)| |[dualblendchainnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dualblendchainnode.markdown)|
|[ GetNormalizedTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#getnormalizedtime-zero-e)|[ Paused](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#paused-zero-engine-docum)| |[dualblendcrossblend](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dualblendcrossblend.markdown)|
|[ IsActive](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#isactive-zero-engine-doc)|[ Time](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#time-zero-engine-documen)| |[dualblenddirectblend](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dualblenddirectblend.markdown)|
|[ PrintNode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#printnode-void)|[ TimeScale](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#timescale-zero-engine-do)| |[dualblendselectivenode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dualblendselectivenode.markdown)|
|[ SetNormalizedTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown#setnormalizedtime-void)| | |[posenode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/posenode.markdown)|


 #  Properties


---  
 #  CollapseToPoseOnFinish : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to collapse to a pose node when finished playing.
> ``` lang=cpp, name=Zilch
> var CollapseToPoseOnFinish : Boolean


---  
 #  Duration : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The duration of the node.
> ``` lang=cpp, name=Zilch
> var Duration : Real


---  
 #  Paused : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Whether or not the node is currently paused.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  Time : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The current time in the node.
> ``` lang=cpp, name=Zilch
> var Time : Real


---  
 #  TimeScale : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> A scalar to dt when updating the node.
> ``` lang=cpp, name=Zilch
> var TimeScale : Real


---  
 #  Methods


---  
 #  Clone : [animationnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/animationnode.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clone() : AnimationNode
> ``` 


---  
 #  CollapseToPose : Void

> Collapses all children to a pose node on the next Update.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CollapseToPose()
> ``` 


---  
 #  GetNormalizedTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GetNormalizedTime() : Real
> ``` 


---  
 #  IsActive : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IsActive() : Boolean
> ``` 


---  
 #  PrintNode : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |tabs|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function PrintNode(tabs : Integer)
> ``` 


---  
 #  SetNormalizedTime : Void

> A value between [0-1].
> |Name|Type|Description|
> |---|---|---|
> |normalizedTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetNormalizedTime(normalizedTime : Real)
> ``` 


---  
 

 