 `Component` `Gameplay`



(NOTE) Defines a new basis for a desired right, up, and forward vector. Provides a bunch of helper functions to change between these spaces and to perform simple look-at behavior.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ComputeSignedAngle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#computesignedangle-zero)|[ AbsoluteAngle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#absoluteangle-zero-engin)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ DebugDrawBases](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#debugdrawbases-void)|[ DefaultOrientationBases](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#defaultorientationbases)| | |
|[ GetLookAtDirectionRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#getlookatdirectionrotati)|[ GlobalUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#globalup-zero-engine-doc)| | |
|[ GetLookAtDirectionWithUpRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#getlookatdirectionwithup)|[ LocalForward](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localforward-zero-engine)| | |
|[ GetLookAtPointRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#getlookatpointrotation-z)|[ LocalOrientationBasis](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localorientationbasis-ze)| | |
|[ GetLookAtPointWithUpRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#getlookatpointwithuprota)|[ LocalRight](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localright-zero-engine-d)| | |
|[ LookAtDirection](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#lookatdirection-void)|[ LocalToOrientationRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localtoorientationrotati)| | |
|[ LookAtDirectionWithUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#lookatdirectionwithup-vo)|[ LocalToWorldRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localtoworldrotation-zer)| | |
|[ LookAtPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#lookatpoint-void)|[ LocalUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#localup-zero-engine-docu)| | |
|[ LookAtPointWithUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#lookatpointwithup-void)|[ OrientationForward](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientationforward-zero)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientation-void)|[ OrientationRight](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientationright-zero-en)| | |
|[ SetLocalLookAtRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#setlocallookatrotation-v)|[ OrientationToLocalRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientationtolocalrotati)| | |
|[ SetWorldLookAtRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#setworldlookatrotation-v)|[ OrientationToWorldRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientationtoworldrotati)| | |
| |[ OrientationUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#orientationup-zero-engin)| | |
| |[ WorldForward](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#worldforward-zero-engine)| | |
| |[ WorldRight](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#worldright-zero-engine-d)| | |
| |[ WorldToLocalRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#worldtolocalrotation-zer)| | |
| |[ WorldToOrientationRotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#worldtoorientationrotati)| | |
| |[ WorldUp](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/orientation.markdown#worldup-zero-engine-docu)| | |


 #  Properties


---  
 #  AbsoluteAngle : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> Get the angle of the object about the up vector.
> ``` lang=cpp, name=Zilch
> var AbsoluteAngle : Real


---  
 #  DefaultOrientationBases : [OrientationBases](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#orientationbases)

> 
> ``` lang=cpp, name=Zilch
> var DefaultOrientationBases : OrientationBases


---  
 #  GlobalUp : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The world-space up vector to use for LookAt operations that don't take an up vector.
> ``` lang=cpp, name=Zilch
> var GlobalUp : Real3


---  
 #  LocalForward : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's forward vector after having been transformed into local space.
> ``` lang=cpp, name=Zilch
> var LocalForward : Real3


---  
 #  LocalOrientationBasis : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> A local-space basis that represents this orientation. If you build a basis from an up of (0, 1, 0), and a forward of (0, 0, -1) then this should result in the identity rotation.
> ``` lang=cpp, name=Zilch
> var LocalOrientationBasis : Quaternion


---  
 #  LocalRight : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's right vector after having been transformed into local space.
> ``` lang=cpp, name=Zilch
> var LocalRight : Real3


---  
 #  LocalToOrientationRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that takes an local space vector into orientation space. For example, this transforms LocalRight into OrientationRight.
> ``` lang=cpp, name=Zilch
> var LocalToOrientationRotation : Quaternion


---  
 #  LocalToWorldRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that transforms a vector from local space into world space. For example, this transforms LocalRight into WorldRight.
> ``` lang=cpp, name=Zilch
> var LocalToWorldRotation : Quaternion


---  
 #  LocalUp : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's up vector after having been transformed into local space.
> ``` lang=cpp, name=Zilch
> var LocalUp : Real3


---  
 #  OrientationForward : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The forward vector in orientation space. This is always the vector (0, 0, -1) but is provided for clarity with transformations.
> ``` lang=cpp, name=Zilch
> var OrientationForward : Real3


---  
 #  OrientationRight : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The right vector in orientation space. This is always the vector (1, 0, 0) but is provided for clarity with transformations.
> ``` lang=cpp, name=Zilch
> var OrientationRight : Real3


---  
 #  OrientationToLocalRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that takes an orientation space vector into local space. For example, this transforms OrientationRight into LocalRight.
> ``` lang=cpp, name=Zilch
> var OrientationToLocalRotation : Quaternion


---  
 #  OrientationToWorldRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that takes an orientation space vector into world space. For example, this transforms OrientationRight into WorldRight.
> ``` lang=cpp, name=Zilch
> var OrientationToWorldRotation : Quaternion


---  
 #  OrientationUp : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The up vector in orientation space. This is always the vector (0, 1, 0) but is provided for clarity with transformations.
> ``` lang=cpp, name=Zilch
> var OrientationUp : Real3


---  
 #  WorldForward : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's forward vector after having been transformed into world space.
> ``` lang=cpp, name=Zilch
> var WorldForward : Real3


---  
 #  WorldRight : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's right vector after having been transformed into world space.
> ``` lang=cpp, name=Zilch
> var WorldRight : Real3


---  
 #  WorldToLocalRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that transforms a vector from world space into local space. For example, this transforms WorldRight into LocalRight.
> ``` lang=cpp, name=Zilch
> var WorldToLocalRotation : Quaternion


---  
 #  WorldToOrientationRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

 `read-only`

> The rotation that takes an world space vector into orientation space. For example, this transforms WorldRight into OrientationRight.
> ``` lang=cpp, name=Zilch
> var WorldToOrientationRotation : Quaternion


---  
 #  WorldUp : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The orientation's up vector after having been transformed into world space.
> ``` lang=cpp, name=Zilch
> var WorldUp : Real3


---  
 #  Methods


---  
 #  ComputeSignedAngle : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Compute the rotation angle between two vectors (in radians)
> |Name|Type|Description|
> |---|---|---|
> |up|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |forward|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |newVector|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ComputeSignedAngle(up : Real3, forward : Real3, newVector : Real3) : Real
> ``` 


---  
 #  DebugDrawBases : Void

> Debug draws the current orientation bases in world space.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugDrawBases()
> ``` 


---  
 #  GetLookAtDirectionRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> Gets the forward to look in the given direction. Keeps the current world up.
> |Name|Type|Description|
> |---|---|---|
> |lookDir|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetLookAtDirectionRotation(lookDir : Real3) : Quaternion
> ``` 


---  
 #  GetLookAtDirectionWithUpRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> Same as GetLookAtDirectionRotation but allows the user to specify the up vector.
> |Name|Type|Description|
> |---|---|---|
> |lookDir|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |up|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetLookAtDirectionWithUpRotation(lookDir : Real3, up : Real3) : Quaternion
> ``` 


---  
 #  GetLookAtPointRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> Get the rotation so that the forward will look at the given point. Keeps the current world up.
> |Name|Type|Description|
> |---|---|---|
> |lookPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetLookAtPointRotation(lookPoint : Real3) : Quaternion
> ``` 


---  
 #  GetLookAtPointWithUpRotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> Same as GetLookAtPointRotation but allows the user to specify the up vector.
> |Name|Type|Description|
> |---|---|---|
> |lookPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |up|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetLookAtPointWithUpRotation(lookPoint : Real3, up : Real3) : Quaternion
> ``` 


---  
 #  LookAtDirection : Void

> Sets the forward to look in the given direction. Keeps the current world up.
> |Name|Type|Description|
> |---|---|---|
> |lookDir|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function LookAtDirection(lookDir : Real3)
> ``` 


---  
 #  LookAtDirectionWithUp : Void

> Same as LookAtDirection but allows the user to specify the up vector.
> |Name|Type|Description|
> |---|---|---|
> |lookDir|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |up|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function LookAtDirectionWithUp(lookDir : Real3, up : Real3)
> ``` 


---  
 #  LookAtPoint : Void

> Sets the forward to look at the given point. Keeps the current world up.
> |Name|Type|Description|
> |---|---|---|
> |lookPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function LookAtPoint(lookPoint : Real3)
> ``` 


---  
 #  LookAtPointWithUp : Void

> Same as LookAtPoint but allows the user to specify the up vector.
> |Name|Type|Description|
> |---|---|---|
> |lookPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |up|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function LookAtPointWithUp(lookPoint : Real3, up : Real3)
> ``` 


---  
 #  Orientation : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Orientation()
> ``` 


---  
 #  SetLocalLookAtRotation : Void

> Set the transform's local rotation such that the orientation's basis vectors will be aligned with the given rotation (assumed to be a look-at rotation constructed from a right, up, and forward)
> |Name|Type|Description|
> |---|---|---|
> |localLookAtRotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetLocalLookAtRotation(localLookAtRotation : Quaternion)
> ``` 


---  
 #  SetWorldLookAtRotation : Void

> Set the transform's world rotation such that the orientation's basis vectors will be aligned with the given rotation (assumed to be a look-at rotation constructed from a right, up, and forward)
> |Name|Type|Description|
> |---|---|---|
> |worldLookAtRotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetWorldLookAtRotation(worldLookAtRotation : Quaternion)
> ``` 


---  
 

 