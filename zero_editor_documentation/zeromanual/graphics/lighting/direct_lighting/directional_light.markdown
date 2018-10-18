A directional light is a light that, as its name suggests, emits light from a specific direction. While the light has a direction, it has no single point from which it emits. Instead, it lights everything within a level from that particular direction. LightIntensity  is an arbitrary scalar applied to the final lighting calculations that includes all lights. One very common use of a directional light is to simulate the sun (and/or moon).

 # Casting Shadows

NOTE: As of now, DirectionalLight is the only type of light that can cast shadows. In the near future, PointLight and the soon-to-be-implemented SpotLight will also have the ability to cast shadows similarly to the way DirectionalLight does.

Directional lights may be created either with or without the ability to cast shadows using either the `CreateDirectionalLightShadows` or `CreateDirectionalLight` commands, respectively.  When created with the ability to cast shadows, the DirectionalLight object will have [Camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/camerasviewportsrenderers.markdown#camera), [CameraViewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/camerasviewportsrenderers.markdown#cameraviewport), and ShadowRenderer components on it. Changing the translation or rotation of the DirectionalLight object will cause the shadows of objects in the scene to change:



![Shadow](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46415.gif) *DirectionalLight rotating around an object*


Shadows cast from a directional light are rendered separately than the other objects on a scene. Therefore, a different renderer, camera, and camera viewport are needed.

 ## CameraViewport

The CameraViewport component on a directional light has different default settings than the one found on the EditorCamera or GameCamera. First, RenderInEditor checkBox and RenderInGame checkBox are set to `true`, while RenderToViewport checkBox is set to `false`. This setup ensures that shadows will be visible both in the editor and in the game, but that the camera viewport will not act as a renderer for the game itself.  Second, RenderOrder  is set to `-1`. This setting ensures that shadows are always rendered before any other camera during runtime (unless, of course, this property on another CameraViewport component is set to a value less than `-1`). Third, ResolutionOrAspect  (in this case, it's referring specifically to the aspect ratio) is set to `[1, 1]`. This setting not only makes the camera a square shape, but also ensures that the shadow map texture isn't squished or skewed.

 ## Camera and ShadowRenderer

This component defines the blue, debug-drawn bounding box visible in the editor. This box, in turn, defines the the volume in which shadows are cast. That is, for an object to cast shadows some part of that object's bounding box must fall within the volume defined by the Camera component. The Size  property's of `64` (which means that the width and height have a value of `64`) is a default of the DirectionalLight archetype, which means that the volume in which shadows will appear within 64 world units defined by the camera.

 ### Shadow Acne

Be wary when increasing the size of the camera as [Resolution](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#shadowresolution) on the ShadowRenderer component is set to `Low`. In fact, at default values, setting Resolution enum to `Low` will cause shadow acne:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46546.png)


This problem may be addressed by increasing the value of the  NormalOffsetBias  property on the DirectionalLight component. The default value is `0.1`, but when changed to `0.2` the shadow acne seen in the previous screenshot is gone:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46548.png)


NormalOffsetBias  biases depth in the direction of an object's surface normal, causing surfaces to "pretend" they're slightly ahead of themselves in regards to shadow mapping. To generalize the issue, there is direct correlation between the values of the NormalOffsetBias , Size , and Resolution enum properties and the presence of shadow acne:

 - When Resolution enum is set `Low`, Size  should be kept at the default value or smaller and NormalOffsetBias  will probably need to be increased in small increments (e.g `0.05` or `0.1` increments) to remove shadow acne.

 - When Resolution enum is set to `Medium`, Size  may be increased to approximately `100` without the need to increase NormalOffsetBias .

 - When Resolution enum is set to `High`, Size  may be increased to approximately `200` without the need to increase NormalOffsetBias .

If one or two directional lights are being used to represent the sun and/or moon, coupling the light object or its parent object's translation to the player character's translation can dramatically reduce the value of Size . If implementing a day/night cycle, the light object may even be parented to the player character itself.

 # Related Materials
 ## Manual

- [ Camera and CameraViewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/camerasviewportsrenderers.markdown)

 ## Code Reference

 [ShadowResolution](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#shadowresolution)

 

 