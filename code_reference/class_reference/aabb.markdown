 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#aabb-void)|[ Center](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#center-zero-engine-docum)| | |
|[ ContainsPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#containspoint-zero-engin)|[ Extents](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#extents-zero-engine-docu)| | |
|[ Expand](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#expand-void)|[ HalfExtents](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#halfextents-zero-engine)| | |
|[ Overlap](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#overlap-zero-engine-docu)|[ Max](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#max-zero-engine-document)| | |
|[ Overlaps](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#overlaps-zero-engine-doc)|[ Min](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#min-zero-engine-document)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#set-void)|[ SurfaceArea](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#surfacearea-zero-engine)| | |
|[ SetInvalid](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#setinvalid-void)|[ Volume](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#volume-zero-engine-docum)| | |
|[ ZeroOut](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown#zeroout-void)| | | |


 #  Properties


---  
 #  Center : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Center : Real3


---  
 #  Extents : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Extents : Real3


---  
 #  HalfExtents : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var HalfExtents : Real3


---  
 #  Max : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Max : Real3


---  
 #  Min : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Min : Real3


---  
 #  SurfaceArea : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var SurfaceArea : Real


---  
 #  Volume : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  Methods


---  
 #  Aabb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Aabb()
> ``` 


---  
 #  Aabb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function Aabb(p0 : Aabb)
> ``` 


---  
 #  Aabb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |center|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Aabb(center : Real3, halfExtents : Real3)
> ``` 


---  
 #  ContainsPoint : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Does this aabb contain the given point?
> |Name|Type|Description|
> |---|---|---|
> |p0|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ContainsPoint(p0 : Real3) : Boolean
> ``` 


---  
 #  Expand : Void

> Expand this aabb to contain the given aabb.
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function Expand(p0 : Aabb)
> ``` 


---  
 #  Expand : [aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)

 `static`

> Creates an aabb that contains the two given aabbs.
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> |p1|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function Expand(p0 : Aabb, p1 : Aabb) : Aabb
> ``` 


---  
 #  Expand : [aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)

 `static`

> Creates an aabb that contains the given aabb and point.
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> |p1|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Expand(p0 : Aabb, p1 : Real3) : Aabb
> ``` 


---  
 #  Expand : Void

> Expand this aabb to contain the given point.
> |Name|Type|Description|
> |---|---|---|
> |p0|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Expand(p0 : Real3)
> ``` 


---  
 #  Overlap : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> This function is deprecated. Use Overlaps instead
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function Overlap(p0 : Aabb) : Boolean
> ``` 


---  
 #  Overlaps : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Does this aabb overlap/intersect the given aabb?
> |Name|Type|Description|
> |---|---|---|
> |p0|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function Overlaps(p0 : Aabb) : Boolean
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |point|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(point : Real3)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |center|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(center : Real3, halfExtents : Real3)
> ``` 


---  
 #  SetInvalid : Void

> Sets this aabb to an invalid aabb (Real3.PositiveMax, Real3.NegativeMin)). This also makes expansion easier.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SetInvalid()
> ``` 


---  
 #  ZeroOut : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ZeroOut()
> ``` 


---  
 

 