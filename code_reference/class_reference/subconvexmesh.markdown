 `Physics`



(NOTE) Contains the indices of a convex mesh. The triangle indices are the primary method to configure this (required for mass computations). The regular indices are used for debug drawing and to reduce intersection tests by removing duplicate points. If left empty, Indices will be auto-filled from the triangle indices.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Indices](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subconvexmesh.markdown#indices-zero-engine-docu)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32object.markdown)| |
| |[ Mesh](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subconvexmesh.markdown#mesh-zero-engine-documen)| | |
| |[ TriangleIndices](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subconvexmesh.markdown#triangleindices-zero-eng)| | |
| |[ Valid](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subconvexmesh.markdown#valid-zero-engine-docume)| | |


 #  Properties


---  
 #  Indices : [multiconvexmeshindexdata](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multiconvexmeshindexdata.markdown)

 `read-only`

> The vertex indices on the main mesh used to generate the convex hull.
> ``` lang=cpp, name=Zilch
> var Indices : MultiConvexMeshIndexData


---  
 #  Mesh : [multiconvexmesh](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multiconvexmesh.markdown)

> The MultiConvexMesh that owns this sub-mesh.
> ``` lang=cpp, name=Zilch
> var Mesh : MultiConvexMesh


---  
 #  TriangleIndices : [multiconvexmeshindexdata](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multiconvexmeshindexdata.markdown)

 `read-only`

> The vertex indices on the main mesh used to generate triangle indices for computing mass information and debug drawing. More indices are needed for determining triangles than for generating the convex mesh.
> ``` lang=cpp, name=Zilch
> var TriangleIndices : MultiConvexMeshIndexData


---  
 #  Valid : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Is this sub-mesh incorrectly configured. Typically means that the indices don't point to valid vertices. Also the number of triangle indices could be incorrect (multiple of 3).
> ``` lang=cpp, name=Zilch
> var Valid : Boolean


---  
 #  Methods


---  
 

 