All [graphical](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphical.markdown) components—2D and 3D alike—inherit from the Graphical base class. As a result there are a number of properties that all graphical components have in common.



![GraphicalProperties](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66457.png)


 # ViewCulling

By default, this property is set to true and the model will be culled if its bounding box goes outside of the view frustum (e.g. off-screen in the case of the game camera). Note that this only applies to the graphical component, so as to not alter any expected behavior. As a general rule, this property should be set to `true` unless there is a good reason not to (e.g. a particle system whose particles should still be visible even if they move outside of their bounding volume as a result of forces). If all Graphicals are drawn whether or not they are within the view frustum of the game camera, it will result in the performance taking a huge hit.

 # VisibilityEvents

When set to `true` the object that owns this graphical component will receive events upon entering or exiting the view frustum of an active camera (such as the game camera). To put it another way, if set to `false`, when the object that owns this graphical component enters an active view frustum, it will not connect to view [GraphicalEvents](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphicalevent.markdown) such as `EnterView` and `ExitView`.

 # OverrideBoundingBox

All graphical objects generate an axis-aligned bounding box (i.e. aabb) according to that's object scale.  If this auto-generated bounding box is not sufficient for whatever reason, it may be redefined manually by the user by setting OverrideBoundingBox checkBox to `true`. When set to `true`, two more properties will become visible that will define the new bounding box: LocalAabbCenter  and LocalAabbHalfExtents .



![OverrideBoundingBox](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47714.png)


Initially, the values of these two properties will be such that they do not change the bounding box from it's originally generated size. LocalAabbCenter  is set to `[0, 0, 0]` by default and any change in the value will offset the bounding box. For example, if the the value was changed to `[2, 5, 0]`, the bounding box would be offset 2 units in the positive x-axis and 5 units in the positive y-axis. LocalAabbHalfExtents  sets the x-, y-, and z-half extents, in local space, that define the size of the box. By default, it is set to `[1, 1, 1]`, which effectively doubles the size of the generated bounding box. The resulting bounding box is a direct result of the scale of the object multiplied with the half-extents. For an object scaled to `[3, 3, 3]` and LocalAabbHalfExtents  set to the `[2, 2, 2]`, the resulting bounding box will have a volume defined by the scale `[12, 12, 12]`, as each half-extent will be `6`.



![ScaledBoundingBox](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66459.png)


 # GroupSortValue

This property should only be used if using a [RenderGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/rendergroups.markdown) that uses `GraphicalSortValue` as its GraphicalSortMethod enum. While GroupSortValue  could be set on an object by object basis, if there is even a moderate amount of graphicals in a project, setting this value for all graphicals through a script—where graphicals can be filtered into discrete groups—is recommended.

 # Material

Every graphical uses a Material, whether it is user-defined or built-in. Information on Materials can be found in the [materials_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown).

 # RelatedMaterials
 ## Manual
- [RenderGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/rendergroups.markdown)
- [materials_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown)

 ## Code Reference
- [graphical](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphical.markdown)
- [graphicalevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphicalevent.markdown)
 

 