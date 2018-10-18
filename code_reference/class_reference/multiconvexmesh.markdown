 `Resource` `Physics`



(NOTE) Represents a collection of convex meshes that was decomposed from a mesh.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ CreateRuntime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#createruntime-zero-engin)|[ Modified](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#modified-zero-engine-doc)|Resource| |
|[ RuntimeClone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#runtimeclone-zero-engine)|[ SubMeshes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#submeshes-zero-engine-do)| | |
|[ UpdateAndNotifyIfModified](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#updateandnotifyifmodifie)|[ Valid](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#valid-zero-engine-docume)| | |
|[ Validate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#validate-zero-engine-doc)|[ Vertices](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown#vertices-zero-engine-doc)| | |


 #  Properties


---  
 #  Modified : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Is the resource currently modified?
> ``` lang=cpp, name=Zilch
> var Modified : Boolean


---  
 #  SubMeshes : [multiconvexmeshsubmeshdata](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmeshsubmeshdata.markdown)

 `read-only`

> A collection of sub-convex meshes.
> ``` lang=cpp, name=Zilch
> var SubMeshes : MultiConvexMeshSubMeshData


---  
 #  Valid : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Is the resource correctly setup? Typically involves a mis-match in indices and vertices.
> ``` lang=cpp, name=Zilch
> var Valid : Boolean


---  
 #  Vertices : [multiconvexmeshvertexdata](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmeshvertexdata.markdown)

 `read-only`

> The vertex buffer data of this mesh.
> ``` lang=cpp, name=Zilch
> var Vertices : MultiConvexMeshVertexData


---  
 #  Methods


---  
 #  CreateRuntime : [multiconvexmesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown)

 `static`

> Creates a MultiConvexMesh for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateRuntime() : MultiConvexMesh
> ``` 


---  
 #  RuntimeClone : [multiconvexmesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/multiconvexmesh.markdown)

> Creates a clone of this mesh for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RuntimeClone() : MultiConvexMesh
> ``` 


---  
 #  UpdateAndNotifyIfModified : Void

> Rebuild all extra mesh information if it is currently modified. This includes things like the center of mass, volume, aabb, edge info and more.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function UpdateAndNotifyIfModified()
> ``` 


---  
 #  Validate : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Check if the mesh is valid. Optionally throw a script exception if it is invalid.
> |Name|Type|Description|
> |---|---|---|
> |throwExceptionIfInvalid|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Validate(throwExceptionIfInvalid : Boolean) : Boolean
> ``` 


---  
 

 