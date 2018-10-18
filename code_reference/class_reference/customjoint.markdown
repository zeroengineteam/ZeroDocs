 `Component` `Physics`



(NOTE) A customizable joint that can be configured in script. The user can create constraints belonging to this joint and set the required values to solve them. Some basic constraint understanding is required. To compute constraints you should listen to Events.ComputeCustomJointInfo.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddConstraint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#addconstraint-void)|[ ConstraintCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#constraintcount-zero-eng)|[joint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/joint.markdown)| |
|[ ClearConstraints](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#clearconstraints-void)| | | |
|[ CreateConstraint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#createconstraint-zero-en)| | | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#customjoint-void)| | | |
|[ GetConstraint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#getconstraint-zero-engin)| | | |
|[ RemoveConstraint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customjoint.markdown#removeconstraint-void)| | | |


 #  Properties


---  
 #  ConstraintCount : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns how many constraints this joint owns.
> ``` lang=cpp, name=Zilch
> var ConstraintCount : Integer


---  
 #  Methods


---  
 #  AddConstraint : Void

> Add a constraint to this joint. This will assert if a joint already owns this constraint.
> |Name|Type|Description|
> |---|---|---|
> |constraint|[customconstraintinfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customconstraintinfo.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddConstraint(constraint : CustomConstraintInfo)
> ``` 


---  
 #  ClearConstraints : Void

> Clear all constraints from this joint (so none will solve).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearConstraints()
> ``` 


---  
 #  CreateConstraint : [customconstraintinfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customconstraintinfo.markdown)

> Create a constraint that is attached to this joint.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateConstraint() : CustomConstraintInfo
> ``` 


---  
 #  CustomJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CustomJoint()
> ``` 


---  
 #  GetConstraint : [customconstraintinfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customconstraintinfo.markdown)

> Returns the constraint at the given index. Will assert if the index is outside the constraint count range.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetConstraint(index : Integer) : CustomConstraintInfo
> ``` 


---  
 #  RemoveConstraint : Void

> If the given constraint belongs to this joint then remove it from the constraints to solve.
> |Name|Type|Description|
> |---|---|---|
> |constraint|[customconstraintinfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customconstraintinfo.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveConstraint(constraint : CustomConstraintInfo)
> ``` 


---  
 

 