 `Event` `Gameplay`



(NOTE) All mouse events that are forwarded to reactive components or the space use this event to add extra data.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ToWorldPlane](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#toworldplane-zero-engine)|[ CameraViewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#cameraviewport-zero-engi)|[mouseevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouseevent.markdown)|[manipulatortoolevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/manipulatortoolevent.markdown)|
|[ ToWorldViewPlane](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#toworldviewplane-zero-en)|[ HitDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#hitdistance-zero-engine)| | |
|[ ToWorldZPlane](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#toworldzplane-zero-engin)|[ HitNormal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#hitnormal-zero-engine-do)| | |
| |[ HitObject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#hitobject-zero-engine-do)| | |
| |[ HitPosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#hitposition-zero-engine)| | |
| |[ HitUv](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#hituv-zero-engine-docume)| | |
| |[ RayDirection](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#raydirection-zero-engine)| | |
| |[ RayStart](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#raystart-zero-engine-doc)| | |
| |[ WorldRay](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/viewportmouseevent.markdown#worldray-zero-engine-doc)| | |


 #  Properties


---  
 #  CameraViewport : [cameraviewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cameraviewport.markdown)

 `read-only`

> Camera viewport that generated this event.
> ``` lang=cpp, name=Zilch
> var CameraViewport : CameraViewport


---  
 #  HitDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The distance away the hit point is. Used with Reactive components.
> ``` lang=cpp, name=Zilch
> var HitDistance : Real


---  
 #  HitNormal : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The normal at the intersection point with an object. Used with Reactive components.
> ``` lang=cpp, name=Zilch
> var HitNormal : Real3


---  
 #  HitObject : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Object hit in ray cast.
> ``` lang=cpp, name=Zilch
> var HitObject : Cog


---  
 #  HitPosition : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The intersection point with an object. Used with Reactive components.
> ``` lang=cpp, name=Zilch
> var HitPosition : Real3


---  
 #  HitUv : [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)

> The uv texture coordinate at the intersection point, if applicable. Used with Reactive components.
> ``` lang=cpp, name=Zilch
> var HitUv : Real2


---  
 #  RayDirection : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Mouse Ray Direction.
> ``` lang=cpp, name=Zilch
> var RayDirection : Real3


---  
 #  RayStart : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Mouse Ray start.
> ``` lang=cpp, name=Zilch
> var RayStart : Real3


---  
 #  WorldRay : [ray](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ray.markdown)

> The world mouse ray.
> ``` lang=cpp, name=Zilch
> var WorldRay : Ray


---  
 #  Methods


---  
 #  ToWorldPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The world mouse position on any arbitrary plane.
> |Name|Type|Description|
> |---|---|---|
> |worldPlaneNormal|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |worldPlanePosition|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ToWorldPlane(worldPlaneNormal : Real3, worldPlanePosition : Real3) : Real3
> ``` 


---  
 #  ToWorldViewPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The world mouse position on the view plane at view depth.
> |Name|Type|Description|
> |---|---|---|
> |viewDepth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ToWorldViewPlane(viewDepth : Real) : Real3
> ``` 


---  
 #  ToWorldZPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The world mouse position on the z plane at depth.
> |Name|Type|Description|
> |---|---|---|
> |worldDepth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ToWorldZPlane(worldDepth : Real) : Real3
> ``` 


---  
 

 