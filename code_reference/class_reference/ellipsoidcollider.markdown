 `Component` `Physics`



(NOTE) Defines the collision volume for an ellipsoid (3 dimensional ellipse) defined by three radius values.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ellipsoidcollider.markdown#ellipsoidcollider-void)|[ Radii](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ellipsoidcollider.markdown#radii-zero-engine-docume)|[collider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collider.markdown)| |
| |[ WorldRadii](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ellipsoidcollider.markdown#worldradii-zero-engine-d)| | |


 #  Properties


---  
 #  Radii : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The x, y, and z radius of the ellipsoid.
> ``` lang=cpp, name=Zilch
> var Radii : Real3


---  
 #  WorldRadii : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The radii of the ellipsoid after transform is applied (scale and rotation).
> ``` lang=cpp, name=Zilch
> var WorldRadii : Real3


---  
 #  Methods


---  
 #  EllipsoidCollider : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function EllipsoidCollider()
> ``` 


---  
 

 