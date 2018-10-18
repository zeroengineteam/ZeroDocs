Imported meshes may be used to apply to a [Model](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/models/model_component.markdown) or [SkinnedModel](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/models/model_component.markdown#skinned-model) component as well as to create a [PhysicsMesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsMesh.markdown) for that object. This page focuses solely on using a mesh for a Model and SkinnedModel. Clicking on a particular mesh in the Library window will open up the ContentComponents of that mesh in the Properties window:

 # ContentComponents for a Sample Mesh

The properties in the ContentComponents are the same as those found in the [Group Import Options](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_scene_assets.markdown#group-import-options), along with a few additional properties. One can fix incorrect values set during import as well as add or remove automatic resource generation (e.g. importing textures and animations from the same .fbx that included the base mesh).

WARNING: All meshes imported from a single .fbx or other scene asset file will have the same values in the properties of the ContentComponents. It is therefore recommended to only import one object per scene asset file.

 # MeshBuilder

The MeshBuilder ContentComponent includes those properties specifically related to an imported mesh (instead of other resources imported in the same file that are associated with the mesh such as animations and textures).

 # AnimationBuilder and AnimationClips

The AnimationBuilder ContentComponent defines clips of animation that have been imported. If importing a single animation, the AnimationClip will be automatically generated and there is nothing more to do. If using a workflow where all animations for a certain mesh are included in the same timeline or track in an asset file, different AnimationClips will need to added for each separate animation, defined by their start and end frames. If using such a workflow, the artist should provide the user with the frame specifications for each distinct animation.

Every AnimationClip can be named, have its start and end frames defined, and its looping mode set (`Default`, `Once`, or `Looping`). Once an AnimationClip is added it is treated like an Animation Resource in Zero and can be accessed in ZilchScript like any other Animation.

 # TextureContent and GeneratedArchetype

These components have no properties and are there only if `ImportTextures` and `GenerateArchetype` are set to true in the Group Import Options window when importing an asset. If a scene asset file has textures in it, but `ImportTextures` was set to false when imported, adding the TextureContent component and reloading the mesh will add the textures to the project Library. If no archetype was created on import, adding GenerateArchetype and reloading will create an archetype in the project Library.

---

 # Related Materials

 ## Manual
- [model_component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/models/model_component.markdown)
- [adding_scene_assets](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_scene_assets.markdown)

 ## Reference
- [model](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/model.markdown)
- [skinnedmodel](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/skinnedmodel.markdown)
- [PhysicsMesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsMesh.markdown) 

 