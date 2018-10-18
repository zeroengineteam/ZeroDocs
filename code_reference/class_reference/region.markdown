 `Component` `Physics`



(NOTE) Regions are used to make PhysicsEffects affect a region of space. Any effects attached to a Cog with a Region will apply to all objects in contact with this region.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ DispatchEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown#dispatchevent-void)|[ WakeUpOnEffectChange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown#wakeuponeffectchange-zer)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown#region-void)| | | |


 #  Properties


---  
 #  WakeUpOnEffectChange : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Determines if all objects in the region should be woken up when an effect is changed. Used to make sure that changes in effects will be applied to an object event if it is asleep.
> ``` lang=cpp, name=Zilch
> var WakeUpOnEffectChange : Boolean


---  
 #  Methods


---  
 #  DispatchEvent : Void

> Dispatches an event to all objects in this region.
> |Name|Type|Description|
> |---|---|---|
> |eventId|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |toSend|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
> ``` lang=cpp, name=Zilch
> function DispatchEvent(eventId : String, toSend : Event)
> ``` 


---  
 #  Region : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Region()
> ``` 


---  
 

 