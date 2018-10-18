 `Component` `Physics`



(NOTE) A controller for a high speed physics based car. The car is controlled with a steer, gas, and brake scalar. The car will raycast wheel positions to try to keep the wheels on the ground and then apply friction and normal forces to propel the car.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ NumberOfWheelsInContact](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#numberofwheelsincontact)|[ Active](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#active-zero-engine-docum)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#physicscar-void)|[ AntiLockBrakes](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#antilockbrakes-zero-engi)| | |
| |[ Brake](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#brake-zero-engine-docume)| | |
| |[ DebugDraw](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#debugdraw-zero-engine-do)| | |
| |[ Gas](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#gas-zero-engine-document)| | |
| |[ GripScalar](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#gripscalar-zero-engine-d)| | |
| |[ MaxSpeed](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#maxspeed-zero-engine-doc)| | |
| |[ MaxTorque](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#maxtorque-zero-engine-do)| | |
| |[ Steer](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#steer-zero-engine-docume)| | |
| |[ TorqueGovernor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#torquegovernor-zero-engi)| | |
| |[ WheelCogs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#wheelcogs-zero-engine-do)| | |
| |[ WheelFrictionFrontRollCoef](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#wheelfrictionfrontrollco)| | |
| |[ WheelFrictionSideRollCoef](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicscar.markdown#wheelfrictionsiderollcoe)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not the car will run any logic at all. If this is false wheels will not work, they will not behave as springs, drive, or anything else.
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  AntiLockBrakes : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Prevents the car from entering dynamic friction when applying brakes. If the brake would start to skid, the brake force is clamped to the max amount that will not slip.
> ``` lang=cpp, name=Zilch
> var AntiLockBrakes : Boolean


---  
 #  Brake : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How much the brake is being pressed [0,1] where 1 is full brake.
> ``` lang=cpp, name=Zilch
> var Brake : Real


---  
 #  DebugDraw : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Whether or not the car should debug draw.
> ``` lang=cpp, name=Zilch
> var DebugDraw : Boolean


---  
 #  Gas : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How much the gas is being pressed [-1,1] where -1 is full reverse.
> ``` lang=cpp, name=Zilch
> var Gas : Real


---  
 #  GripScalar : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Artificially increases the grip of the car (where 2 is twice the grip). The total grip scalar is computed as CarGripScalar * WheelGripScalar so the total car can be easily tweaked while allowing individual wheel tweaks.
> ``` lang=cpp, name=Zilch
> var GripScalar : Real


---  
 #  MaxSpeed : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The desired maximum speed of the car. Similar to a speed governor.
> ``` lang=cpp, name=Zilch
> var MaxSpeed : Real


---  
 #  MaxTorque : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The maximum torque the engine can apply to try to reach the max speed.
> ``` lang=cpp, name=Zilch
> var MaxTorque : Real


---  
 #  Steer : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How much the wheel is being steered. This is measured in radians about this object's y-axis.
> ``` lang=cpp, name=Zilch
> var Steer : Real


---  
 #  TorqueGovernor : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Governs the max torque that the engine can apply. This is used to keep the wheels from spinning out (slipping) when too high of a torque is applied. If the tires would slip, the engine will apply the maximum torque for the tires to not slip.
> ``` lang=cpp, name=Zilch
> var TorqueGovernor : Boolean


---  
 #  WheelCogs : [carwheelarray](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/carwheelarray.markdown)

 `read-only`

> Read-only array of wheels belonging to this car.
> ``` lang=cpp, name=Zilch
> var WheelCogs : CarWheelArray


---  
 #  WheelFrictionFrontRollCoef : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Coefficient used to apply the forward friction force closer to the car's center of mass. 1 applies the force at the wheel position, 0 applies the force at the point along the contact normal closest to the center of mass.
> ``` lang=cpp, name=Zilch
> var WheelFrictionFrontRollCoef : Real


---  
 #  WheelFrictionSideRollCoef : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Coefficient used to apply the side friction force closer to the car's center of mass. 1 applies the force at the wheel position, 0 applies the force at the point along the contact normal closest to the center of mass.
> ``` lang=cpp, name=Zilch
> var WheelFrictionSideRollCoef : Real


---  
 #  Methods


---  
 #  NumberOfWheelsInContact : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

> The number of wheels currently in contact with an object.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function NumberOfWheelsInContact() : Integer
> ``` 


---  
 #  PhysicsCar : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PhysicsCar()
> ``` 


---  
 

 