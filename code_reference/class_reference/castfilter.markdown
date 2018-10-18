 `Physics`

(NOTE) Filter for casting operations in physics. Allows basic filtering such as static or dynamic objects, advanced filters such as collision groups, and custom filters via an event callback.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown#castfilter-void)|[ CallbackEventName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown#callbackeventname-zero-e)|[basecastfilter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/basecastfilter.markdown)| |
| |[ CallbackObject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown#callbackobject-object)| | |
| |[ CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown#collisiongroup-zero-engi)| | |
| |[ IgnoreCog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown#ignorecog-zero-engine-do)| | |


 #  Properties


---  
 #  CallbackEventName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> The name of the event to invoke on the callback object.
> ``` lang=cpp, name=Zilch
> var CallbackEventName : String


---  
 #  CallbackObject : Object

> An object to invoke a callback on (via the callback name) to see if an object in a cast should be skipped.
> ``` lang=cpp, name=Zilch
> var CallbackObject : Object


---  
 #  CollisionGroup : [collisiongroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown)

> Should this cast behave like it belongs to a collision group? Uses the current space's CollisionTable for filtering logic.
> ``` lang=cpp, name=Zilch
> var CollisionGroup : CollisionGroup


---  
 #  IgnoreCog : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> A cog to ignore during casts.
> ``` lang=cpp, name=Zilch
> var IgnoreCog : Cog


---  
 #  Methods


---  
 #  CastFilter : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CastFilter()
> ``` 


---  
 #  CastFilter : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ||[castfilter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castfilter.markdown)| |
> ``` lang=cpp, name=Zilch
> function CastFilter( : CastFilter)
> ``` 


---  
 

 