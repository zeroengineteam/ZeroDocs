 `Resource` `Physics`



(NOTE) Describes material properties of a collider mainly used during collision resolution.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ CreateRuntime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#createruntime-zero-engin)|[ Density](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#density-zero-engine-docu)|[dataresource](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dataresource.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#physicsmaterial-void)|[ Friction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#friction-zero-engine-doc)| | |
|[ RuntimeClone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#runtimeclone-zero-engine)|[ FrictionImportance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#frictionimportance-zero)| | |
|[ UpdateAndNotifyIfModified](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#updateandnotifyifmodifie)|[ HighPriority](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#highpriority-zero-engine)| | |
| |[ Restitution](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#restitution-zero-engine)| | |
| |[ RestitutionImportance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown#restitutionimportance-ze)| | |


 #  Properties


---  
 #  Density : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Density is used to determine the mass of an object. Mass is computed as density * volume. Density can be set to exactly 0 to produce a massless object, however this should only be done with children objects to add collision without affecting mass.
> ``` lang=cpp, name=Zilch
> var Density : Real


---  
 #  Friction : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How slippery or rough the object is. When friction is 0 the object will be slippery. As friction increases, sliding objects will stop quicker. The friction of two object's are combined with the formula sqrt(a * b).
> ``` lang=cpp, name=Zilch
> var Friction : Real


---  
 #  FrictionImportance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Determines which object's friction should be used. If object A's friction importance value is larger than object B's then object A's friction will be used. If both importance values are the same then the default combination logic will be used (see the description of Friction for details).
> ``` lang=cpp, name=Zilch
> var FrictionImportance : Real


---  
 #  HighPriority : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Deprecated. Use RestitutionImportance instead.
> ``` lang=cpp, name=Zilch
> var HighPriority : Boolean


---  
 #  Restitution : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much an object will bounce during a collision. Values should be in the range [0,1] where 0 is an inelastic collision and 1 is a fully elastic collision. Restitution is computed as the max of the two objects. Note: due to solving constraints with baumgarte, energy will not be perfectly conserved with a restitution 1.
> ``` lang=cpp, name=Zilch
> var Restitution : Real


---  
 #  RestitutionImportance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Determines which object's restitution should be used. If object A's restitution importance value is larger than object B's then object A's restitution will be used. If both importance values are the same then the default combination logic will be used (see the description of Restitution for details).
> ``` lang=cpp, name=Zilch
> var RestitutionImportance : Real


---  
 #  Methods


---  
 #  CreateRuntime : [physicsmaterial](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown)

 `static`

> Creates a PhysicsMaterial for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateRuntime() : PhysicsMaterial
> ``` 


---  
 #  PhysicsMaterial : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PhysicsMaterial()
> ``` 


---  
 #  RuntimeClone : [physicsmaterial](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown)

> Creates a clone of this material for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RuntimeClone() : PhysicsMaterial
> ``` 


---  
 #  UpdateAndNotifyIfModified : Void

> After modifying this resource, notify anyone using it to update now instead of at the next physics update.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function UpdateAndNotifyIfModified()
> ``` 


---  
 

 