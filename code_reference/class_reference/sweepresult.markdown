 `Physics`

(NOTE) Cast result from performing a sweep test.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#sweepresult-void)|[ OtherCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#othercollider-zero-engin)| | |
| |[ OtherObject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#otherobject-zero-engine)| | |
| |[ Penetration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#penetration-zero-engine)| | |
| |[ Time](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#time-zero-engine-documen)| | |
| |[ WorldNormalTowardsOther](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#worldnormaltowardsother)| | |
| |[ WorldNormalTowardsSelf](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#worldnormaltowardsself-z)| | |
| |[ WorldPoint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown#worldpoint-zero-engine-d)| | |


 #  Properties


---  
 #  OtherCollider : [collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collider.markdown)

 `read-only`

> The other collider being hit.
> ``` lang=cpp, name=Zilch
> var OtherCollider : Collider


---  
 #  OtherObject : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> The other cog being hit.
> ``` lang=cpp, name=Zilch
> var OtherObject : Cog


---  
 #  Penetration : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The amount of overlap with this object. Will typically be zero unless the objects start in contact.
> ``` lang=cpp, name=Zilch
> var Penetration : Real


---  
 #  Time : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The time of impact that this collision first happens.
> ``` lang=cpp, name=Zilch
> var Time : Real


---  
 #  WorldNormalTowardsOther : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The contact normal pointing from the sweeping object towards the other object.
> ``` lang=cpp, name=Zilch
> var WorldNormalTowardsOther : Real3


---  
 #  WorldNormalTowardsSelf : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The contact normal pointing from the other object towards the sweeping object.
> ``` lang=cpp, name=Zilch
> var WorldNormalTowardsSelf : Real3


---  
 #  WorldPoint : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The point of intersection in world-space.
> ``` lang=cpp, name=Zilch
> var WorldPoint : Real3


---  
 #  Methods


---  
 #  SweepResult : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SweepResult()
> ``` 


---  
 #  SweepResult : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ||[sweepresult](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sweepresult.markdown)| |
> ``` lang=cpp, name=Zilch
> function SweepResult( : SweepResult)
> ``` 


---  
 
  
  
  
  
  
  
  

 