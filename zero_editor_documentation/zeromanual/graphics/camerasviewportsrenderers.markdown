A [cameraviewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cameraviewport.markdown) draws to an on-screen or off-screen texture. Whether it is visible to in the editor or game depends on whether RenderToViewport checkBox is set to `true`.  It references both a [camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown) component and a [Renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown) component from their respective cogs to render that scene from the perspective of the camera.  As long as there are single instances of these components, it doesn't matter what cog they're on.  If a game has a HUD, two renderers may be necessary and therefore two seperate renderer cogs.  If a game supports splitscreen, both the `CameraViewport` and `Camera` should be duplicated onto another cog. A single CameraViewport can be used to reference multiple Camera objects at different times. A Camera, however, cannot generally be referenced by multiple CameraViewports. For example, if a script sets a CameraViewport's Camera reference to a Camera that is already being referenced by a CameraViewport, the one in the script will "steal" the reference, removing it from the CameraViewport that originally had it.

By default the Camera and CameraViewport components are on the object called "GameCamera" where the DeferredRenderer is found on the Renderer object. This is useful for game scripting as a reference to the camera can be obtained through `CameraViewport.Camera` in order to change it.

 # CameraViewport


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46327.png) *CameraViewport Component*


(NOTE)**Where does the CameraViewport render to?**
The camera can draw onto both the editor window and the game session window.  By default, the `EditorCamera` has RenderInEditor checkBox set to `true` and RenderInGame checkBox set to `false`. As long as RenderToViewport checkBox is also set to `true`, it will render in the editor window and not the game session window.

 ## Viewport Placement
The position and scale of each viewport is controlled with NormalizedSize , NormalizedOffset , ResolutionOrAspect , and [ViewportScaling](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#viewportscaling).  When placing viewports, the dimentions of the game session window are in the normalized range `[0,1]` on both the x and y axes.  `(0,0)` is then the top left corner and `(1,1)` is the bottom right corner.  Below is an example of a camera viewport taking up the whole screen:



![CameraViewport](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47642.png) *Default Single CameraViewport*


 ### Viewport Scaling
ViewportScaling drop-down menu sets the method of fitting the viewport to the region defined by the viewport placement.  Below is a brief description of what each mode does.

| Viewport Fitting Method | Description |
| -- | -- |
| `Fill` | The viewport fills the entire window size |
| `LetterBox` | Viewport aspect ratio is always preserved and gaps are filled in with margins. |
| `Exact` | The viewport is not scaled |
| `LargestMultiple` | The viewport is the largest multiple of the resolution that fits in the window |

 ### Render Order

Render order sets the value by which the CameraViewport should be rendered relative to other CameraViewports (such as the one on a [directional_light](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/lighting/direct_lighting/directional_light.markdown)), where the viewport with the lowest value is rendered first and the one with the highest value is rendered last.

 #### Viewport Layering
The viewports exist in 2D, so there's no Z-axis to sort our viewports on.  Instead, viewports are layered in the order they're drawn.  The draw order is determined first by the integer value RenderOrder , where a high value is drawn later.  If two viewports are on the same layer, the viewport with the cog earlier in the Objects window window draws first.

When a mouse event is sent to the window, it's forwarded to the topmost viewport containing the cursor.  If ForwardViewportEvents checkBox is on, the cursor will then be sent to viewports on underlying layers.  For example, a first person shooter might have a hud map on a separate viewport, but the mouse tracking should work even when the mouse is over the hud.  Mouse events should be sent through the hud viewport, and therefore its CameraViewport should have ForwardViewportEvents checkBox on.

 ## Camera
The cog considered to be the `Camera` is whatever the `CameraViewport` references with CameraPath cogPath.  The `Camera` cog should also have a `Camera` component, or else the viewport wont be rendered.



![Camera](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47645.png) *Camera Component*


 ### Perspective vs. Orthographic
Changing the shape of the view frustum has a significant impact on how objects are viewed in the world.  Usually in a 2D setting, [PerspectiveMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#perspectivemode) is set to `Orthographic` while with 3D applications PerspectiveMode drop-down menu is set to `Perspective`.  Objects in a `Perspective` view and the distances between them will appear smaller as they move away from the camera.  2D games often work with the assumption that everything is approximately the same distance from the camera, and so objects that move away from an `Orthographic` camera will appear the same.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46825.png) *`Perspective` camera(left) vs. `Orthographic` camera(right)*


(NOTE)**Parallaxing** Even if the camera has an orthographic perspective, the illusion of depth is still possible.  Instead of just one universal depth, the new assumption is that there are a set number of layers for an object, often refered to as foregrounds and backgrounds.  For an example, try the [Parallaxing Background](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/graphics/parallaxbackground.markdown) tutorial.

NOTE: The method of controlling the viewport size changes with different viewing frustums.  When PerspectiveMode drop-down menu is set to `Perspective`, the FieldOfView  parameter represents the vertical angle that the frustum makes from the camera eye outward.  When PerspectiveMode drop-down menu is set to `Orthographic`, the Size  parameter represents the height that the camera sees in world space.

 ## Related Materials
 ### Manual
- [Renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer.markdown)

 ### Reference
- [cameraviewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cameraviewport.markdown)
- [camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown) 

 