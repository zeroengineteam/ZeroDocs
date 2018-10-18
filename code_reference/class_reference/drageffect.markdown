 `Component` `Physics`



(NOTE) Applies drag or damping forces to slow down an object's linear and angular velocity. Drag is computed as a simple linear approximation of the drag force. Damping is a linear approximation of a drag acceleration. This means that damping affects all objects the same (mass independent).

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/drageffect.markdown#drageffect-void)|[ AngularDamping](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/drageffect.markdown#angulardamping-zero-engi)|[physicseffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicseffect.markdown)| |
| |[ AngularDrag](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/drageffect.markdown#angulardrag-zero-engine)| | |
| |[ LinearDamping](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/drageffect.markdown#lineardamping-zero-engin)| | |
| |[ LinearDrag](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/drageffect.markdown#lineardrag-zero-engine-d)| | |


 #  Properties


---  
 #  AngularDamping : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Angular damping coefficient for applying an angular drag acceleration (accel = -kw). Note: this affects objects the same regardless of mass.
> ``` lang=cpp, name=Zilch
> var AngularDamping : Real


---  
 #  AngularDrag : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The angular drag coefficient for applying an angular drag force (T = -kw).
> ``` lang=cpp, name=Zilch
> var AngularDrag : Real


---  
 #  LinearDamping : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Linear damping coefficient for applying a linear drag acceleration (accel = -bv). Note: this affects objects the same regardless of mass.
> ``` lang=cpp, name=Zilch
> var LinearDamping : Real


---  
 #  LinearDrag : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The linear drag coefficient for applying a linear drag force (F = -bv).
> ``` lang=cpp, name=Zilch
> var LinearDrag : Real


---  
 #  Methods


---  
 #  DragEffect : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DragEffect()
> ``` 


---  
 

 