 `Physics`

(NOTE) Information to represent a constraint to be solved. The main information that needs to be set here is the Jacobian and error. A constraint will enforce that the relative velocities along the Jacobian are equal to zero (ignoring error correction or motors).

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ComputeMotor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#computemotor-void)|[ Active](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#active-zero-engine-docum)|[referencecountedeventobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/referencecountedeventobject.markdown)| |
|[ ComputeSpring](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#computespring-void)|[ Angular0](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#angular0-zero-engine-doc)| | |
|[ DetachFromOwner](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#detachfromowner-void)|[ Angular1](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#angular1-zero-engine-doc)| | |
|[ IsOwned](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#isowned-zero-engine-docu)|[ Baumgarte](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#baumgarte-zero-engine-do)| | |
|[ SetErrorAndBias](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#seterrorandbias-void)|[ Bias](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#bias-zero-engine-documen)| | |
|[ SetJacobian](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#setjacobian-void)|[ EffectiveMass](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#effectivemass-zero-engin)| | |
| |[ Error](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#error-zero-engine-docume)| | |
| |[ Gamma](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#gamma-zero-engine-docume)| | |
| |[ Impulse](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#impulse-zero-engine-docu)| | |
| |[ Linear0](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#linear0-zero-engine-docu)| | |
| |[ Linear1](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#linear1-zero-engine-docu)| | |
| |[ MaxImpulse](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#maximpulse-zero-engine-d)| | |
| |[ MinImpulse](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#minimpulse-zero-engine-d)| | |
| |[ Owner](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#owner-zero-engine-docume)| | |
| |[ SolvePosition](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customconstraintinfo.markdown#solveposition-zero-engin)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is this constraint currently active?
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  Angular0 : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> Angular portion of objectA's Jacobian.
> ``` lang=cpp, name=Zilch
> var Angular0 : Real3


---  
 #  Angular1 : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> Angular portion of objectB's Jacobian.
> ``` lang=cpp, name=Zilch
> var Angular1 : Real3


---  
 #  Baumgarte : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The baumgarte term used to correct error. This should typically be set in initialization (per constraint) and then left alone. Default value is 5.
> ``` lang=cpp, name=Zilch
> var Baumgarte : Real


---  
 #  Bias : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The bias is used to apply energy into the system. Typically, bias is combined with Error and Baumgarte to fix error. Bias is also used for motors and springs to drive the constraint.
> ``` lang=cpp, name=Zilch
> var Bias : Real


---  
 #  EffectiveMass : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The effective mass of the constraint. This is typically set by calling SetJacobian.
> ``` lang=cpp, name=Zilch
> var EffectiveMass : Real


---  
 #  Error : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The error of the constraint. This should typically be set via the SetError function.
> ``` lang=cpp, name=Zilch
> var Error : Real


---  
 #  Gamma : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Gamma is used to soften constraints. This should typically never be manually set. Instead, it is set when configuring the constraint to act like a spring.
> ``` lang=cpp, name=Zilch
> var Gamma : Real


---  
 #  Impulse : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The total accumulated impulse of this constraint. If you want to not use warm-starting then clear this value every frame.
> ``` lang=cpp, name=Zilch
> var Impulse : Real


---  
 #  Linear0 : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> Linear portion of objectA's Jacobian.
> ``` lang=cpp, name=Zilch
> var Linear0 : Real3


---  
 #  Linear1 : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> Linear portion of objectB's Jacobian.
> ``` lang=cpp, name=Zilch
> var Linear1 : Real3


---  
 #  MaxImpulse : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The max impulse magnitude allowed for the constraint.
> ``` lang=cpp, name=Zilch
> var MaxImpulse : Real


---  
 #  MinImpulse : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The min impulse magnitude allowed for the constraint.
> ``` lang=cpp, name=Zilch
> var MinImpulse : Real


---  
 #  Owner : [customjoint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customjoint.markdown)

 `read-only`

> What joint currently owns this constraint.
> ``` lang=cpp, name=Zilch
> var Owner : CustomJoint


---  
 #  SolvePosition : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Should this constraint solve position directly or use baumgarte correction? Toggling SolvePosition should be done before setting any other values (ideally in initialization). Setting a constraint to be a motor or a spring will turn off position correction as an error bias must be used to solve those scenarios.
> ``` lang=cpp, name=Zilch
> var SolvePosition : Boolean


---  
 #  Methods


---  
 #  ComputeMotor : Void

> Sets this constraint as a motor (i.e. a constraint that drives movement along the Jacobian direction at a certain speed). The motor has a min and max impulse value that can be solved (typically -value, +value). If you set this as a motor, you should do so last. Motors should typically be their own constraint unlike springs.
> |Name|Type|Description|
> |---|---|---|
> |targetSpeed|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |minImpulse|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |maxImpulse|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ComputeMotor(targetSpeed : Real, minImpulse : Real, maxImpulse : Real)
> ``` 


---  
 #  ComputeSpring : Void

> Given the currently set mass and error, fix the constraint to be soft (i.e. solve the constraint like a spring). The spring fixes the constraint using the given frequency (oscillations per second) and damping ratio (0 is no damping, 1 is critical damping).
> |Name|Type|Description|
> |---|---|---|
> |frequencyHz|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |dampRatio|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ComputeSpring(frequencyHz : Real, dampRatio : Real)
> ``` 


---  
 #  DetachFromOwner : Void

> Remove this constraint from whatever joint owns it. This is equivalent to "this.Owner.RemoveConstraint(this)".
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DetachFromOwner()
> ``` 


---  
 #  IsOwned : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is this constraint currently owned by a joint? (Equivalent to "this.Owner != null").
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IsOwned() : Boolean
> ``` 


---  
 #  SetErrorAndBias : Void

> Set the position error of the constraint. This also sets the bias of the constraint (used to actually correct the error). If you want to set this constraint as a motor you should not call this function (or call it first). If you want to set this as a spring then make sure you call this first.
> |Name|Type|Description|
> |---|---|---|
> |error|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetErrorAndBias(error : Real)
> ``` 


---  
 #  SetJacobian : Void

> Set the Jacobian of this constraint (and the effective mass).
> |Name|Type|Description|
> |---|---|---|
> |linear0|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |angular0|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |linear1|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |angular1|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetJacobian(linear0 : Real3, angular0 : Real3, linear1 : Real3, angular1 : Real3)
> ``` 


---  
 
  
  
  
  
  
  
  

 