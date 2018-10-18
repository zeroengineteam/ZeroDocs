[ RenderGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendergroup.markdown) resources act as categories for [ Materials](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown). In a [Renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer.markdown) script, when adding a RenderPass task, a RenderGroup is used to specify which set of objects is to be drawn by that render task. When that render task is executed, all Graphicals in the scene that are using a Material that is categorized as that RenderGroup will be drawn.

 # RenderGroup usage in the DeferredRenderer
A variety of RenderGroup usage examples can be found in the DeferredRenderer resource script. The table below provides some brief descriptions for how it uses different groups of objects to define different steps of the rendering pipeline, in the order they're used.

| RenderGroup | Usage Description |
| -- | -- |
| `Opaque` | Renders scene geometry and PBR attributes to buffers that are used throughout the pipeline. |
| `OpaqueDoubleSided` | Same as Opaque but for backface triangle culling to be disabled. |
| `Lights` | Renders lights to detect overlaps with scene geometry to perform light calculations. |
| `AdditiveBlend` | Renders additively to the lighting results so that objects can invoke the Bloom effect if enabled. |
| `AlphaBlend` | Renders with semi-transparency after lighting effects. |
| `DebugDraw` | Same as AlphaBlend but is a different RenderGroup so debug drawing can be arbitrarily disabled. |
| `DebugDrawOnTop` | Same as DebugDraw but does not depth test with scene geometry, so objects are not occluded. |

 # Assigning RenderGroups
To assign a RenderGroup to a Material, open the Material in the Properties window window. Under the RenderGroups drop-down menu dropdown are all the RenderGroups currently assigned to that Material. Assign a new RenderGroup by clicking {nav icon=square-o, name=Add RenderGroup...} and select one from the list. Clicking on one in the current list will select that RenderGroup in the Properties window window and clicking the x button will remove it from the list.



![DefaultRenderGroups](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47760.png)


While this way of assigning RenderGroups is sufficient in most cases, there may be times when an existing Material should have a RenderGroup but the Material either can't or shouldn't be modified. For this reason, a RenderGroup can also reference a Material by selecting a RenderGroup and adding a Material to its list in the same way. If either or both resources reference one another then that Material belongs to that RenderGroup.



![AddMatToGroup](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66419.png)


(NOTE)**For Convenience** If either a RenderGroup or Material reference one another, the ReferencedBy drop-down menu list displays which resources are referencing it. Resources can also be selected from this list by clicking on them.![ReferencedBy](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66421.png)

 # Sort Method
No matter what the renderer is, the order that graphicals are drawn will almost always be important.  In a 3D game, depth tests can be used instead of any sorting.  In a 2D game, where every graphical shares the same z coordinate the player should be drawn after the background.  In some cases like this, usual Z-based sorting methods wont work.  On each RenderGroup, there's a GraphicalSortMethod drop-down menu property that defines how graphicals in that RenderGroup are sorted.  Below are all the sorting methods and what they do:

| Sort Method | Description |
| -- | -- |
| `None` | No sorting is done |
| `GraphicalSortValue` | Graphicals are sorted by their GroupSortValue  |
| `BackToFrontView` | Graphicals are sorted back to front on the View space Z axis |
| `BackToFrontZ` | Graphicals are sorted back to front on the World space Z axis |
| `FrontToBackView` | Graphicals are sorted front to back on the View space Z axis |
| `FrontToBackZ` | Graphicals are sorted front to back on the World space Z axis |
| `SortEvent` | Sorting is done by a value handled in the SortEvent |

 # Creating RenderGroups
To create a RenderGroup, use [Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Add](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#add) or the Add button button.  From the resource list, select `RenderGroup  > DefaultRenderGroup`:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46036.png)


 # Related Materials
 ## Manual
- [Renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer.markdown)
- [Deferred and Forward Renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown)

 ## Reference
- [rendergroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendergroup.markdown) 

 