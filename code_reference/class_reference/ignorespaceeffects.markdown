 `Component` `Physics`



(NOTE) Allows a cog to ignore certain effect types (such as gravity or drag) that are being applied to the entire space (effects on Space or LevelSettings).

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetIgnoreState](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#getignorestate-zero-engi)|[ IgnoreBuoyancy](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorebuoyancy-zero-engi)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorespaceeffects-void)|[ IgnoreCustom](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorecustom-zero-engine)| | |
|[ SetIgnoreState](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#setignorestate-void)|[ IgnoreDrag](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignoredrag-zero-engine-d)| | |
| |[ IgnoreFlow](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignoreflow-zero-engine-d)| | |
| |[ IgnoreForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignoreforce-zero-engine)| | |
| |[ IgnoreGravity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignoregravity-zero-engin)| | |
| |[ IgnorePointForce](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorepointforce-zero-en)| | |
| |[ IgnorePointGravity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorepointgravity-zero)| | |
| |[ IgnoreThrust](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorethrust-zero-engine)| | |
| |[ IgnoreTorque](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignoretorque-zero-engine)| | |
| |[ IgnoreVortex](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorevortex-zero-engine)| | |
| |[ IgnoreWind](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ignorespaceeffects.markdown#ignorewind-zero-engine-d)| | |


 #  Properties


---  
 #  IgnoreBuoyancy : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore buoyancy effects.
> ``` lang=cpp, name=Zilch
> var IgnoreBuoyancy : Boolean


---  
 #  IgnoreCustom : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore custom effects.
> ``` lang=cpp, name=Zilch
> var IgnoreCustom : Boolean


---  
 #  IgnoreDrag : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore drag effects.
> ``` lang=cpp, name=Zilch
> var IgnoreDrag : Boolean


---  
 #  IgnoreFlow : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore flow effects.
> ``` lang=cpp, name=Zilch
> var IgnoreFlow : Boolean


---  
 #  IgnoreForce : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore force effects.
> ``` lang=cpp, name=Zilch
> var IgnoreForce : Boolean


---  
 #  IgnoreGravity : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore gravity effects.
> ``` lang=cpp, name=Zilch
> var IgnoreGravity : Boolean


---  
 #  IgnorePointForce : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore point force effects.
> ``` lang=cpp, name=Zilch
> var IgnorePointForce : Boolean


---  
 #  IgnorePointGravity : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore point gravity effects.
> ``` lang=cpp, name=Zilch
> var IgnorePointGravity : Boolean


---  
 #  IgnoreThrust : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore thrust effects.
> ``` lang=cpp, name=Zilch
> var IgnoreThrust : Boolean


---  
 #  IgnoreTorque : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore torque effects.
> ``` lang=cpp, name=Zilch
> var IgnoreTorque : Boolean


---  
 #  IgnoreVortex : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore vortex effects.
> ``` lang=cpp, name=Zilch
> var IgnoreVortex : Boolean


---  
 #  IgnoreWind : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not to ignore wind effects.
> ``` lang=cpp, name=Zilch
> var IgnoreWind : Boolean


---  
 #  Methods


---  
 #  GetIgnoreState : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Should the given effect type be ignored?
> |Name|Type|Description|
> |---|---|---|
> |effectType|[PhysicsEffectType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#physicseffecttype)| |
> ``` lang=cpp, name=Zilch
> function GetIgnoreState(effectType : PhysicsEffectType) : Boolean
> ``` 


---  
 #  IgnoreSpaceEffects : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IgnoreSpaceEffects()
> ``` 


---  
 #  SetIgnoreState : Void

> Set if an effect type should be ignored.
> |Name|Type|Description|
> |---|---|---|
> |effectType|[PhysicsEffectType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#physicseffecttype)| |
> |ignore|[boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetIgnoreState(effectType : PhysicsEffectType, ignore : Boolean)
> ``` 


---  
 

 