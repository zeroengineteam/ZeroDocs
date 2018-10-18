 `Event` `Physics`



(NOTE) Allows a user to filter out an object during any cast in physics.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ FilterState](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/castfilterevent.markdown#filterstate-zero-engine)|[event](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/event.markdown)| |
| |[ Object](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/castfilterevent.markdown#object-zero-engine-docum)| | |


 #  Properties


---  
 #  FilterState : [CastFilterState](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#castfilterstate)

> When filtering should we accept or reject this cog? Alternatively we can let the default cast filter logic run.
> ``` lang=cpp, name=Zilch
> var FilterState : CastFilterState


---  
 #  Object : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

 `read-only`

> The object being tested in this cast.
> ``` lang=cpp, name=Zilch
> var Object : Cog


---  
 #  Methods


---  
 

 