 `Physics`

(NOTE) Used to filter objects during cast operations.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ IgnoreChildren](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basecastfilter.markdown#ignorechildren-zero-engi)| |[castfilter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/castfilter.markdown)|
| |[ IgnoreDynamic](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basecastfilter.markdown#ignoredynamic-zero-engin)| | |
| |[ IgnoreGhost](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basecastfilter.markdown#ignoreghost-zero-engine)| | |
| |[ IgnoreKinematic](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basecastfilter.markdown#ignorekinematic-zero-eng)| | |
| |[ IgnoreStatic](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basecastfilter.markdown#ignorestatic-zero-engine)| | |


 #  Properties


---  
 #  IgnoreChildren : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> This flag is currently only used for SweepCollider tests on PhysicsSpace. This is used to ignore all objects that are a child of the Collider that is being swept.
> ``` lang=cpp, name=Zilch
> var IgnoreChildren : Boolean


---  
 #  IgnoreDynamic : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Should Colliders with RigidBodies marked Dynamic be ignored during casts?
> ``` lang=cpp, name=Zilch
> var IgnoreDynamic : Boolean


---  
 #  IgnoreGhost : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Should Colliders marked Ghost be ignored during casts?
> ``` lang=cpp, name=Zilch
> var IgnoreGhost : Boolean


---  
 #  IgnoreKinematic : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Should Colliders with RigidBodies marked Kinematic be ignored during casts?
> ``` lang=cpp, name=Zilch
> var IgnoreKinematic : Boolean


---  
 #  IgnoreStatic : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Should Colliders with RigidBodies marked Static be ignored during casts? Note: Collider's with no RigidBody are treated as static.
> ``` lang=cpp, name=Zilch
> var IgnoreStatic : Boolean


---  
 #  Methods


---  
 

 