The Model component allows the user to assign a [Mesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/mesh.markdown) and a [ Material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown) to an object.

 # Material and Mesh

These properties are where the Material and Mesh resources for the model are set. If a model has been imported using a scene asset file,  the archetype for the object will have the Mesh associated with a specific object already set. By default, the Material will be set to the ZeroMaterial until changed by the user.  If using the SkinnedModel component, the Mesh resource should be a skinned mesh. 

 # Skinned Model

The only property the SkinnedModel component has that the Model component does not is SkeletonPath. When a skinned mesh is imported, SkeletonPath is automatically set to whatever object the animation takes as its first target (i.e. the root object of a skeleton of the generated hierarchy).  The object that SkeletonPath points to should have the Skeleton component on it as well as being the root object of the entire skeleton (i.e. the parent object of all of the bone objects). If SkeletonPath is set incorrectly, the object will fail to animate as the SkinnedModel receives all of its transformation data from the skeleton.

 # Related Materials
 ## Reference
- [Model](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/model.markdown)
- [SkinnedModel](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/skinnedmodel.markdown)
- [Mesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/mesh.markdown)
- [Material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/material.markdown)
 
  
  
  
  
  
  
  

 