
 # Theory
Screen Space Ambient Occlusion(SSAO) is a method of simulating Ambient Occlusion.  Ambient Occlusion refers to the amount a point on a surface is occluded by objects.  A shadow effect occurs, but the shadow doesn't come from any particular light source.  It comes from the ambient light, hence the name.

Specifically, SSAO uses the depth of the visible pixels to compute the AO map, which is then applied to the light buffer of the [Deferred Renderer](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown).

(WARNING)**Performance Impact** SSAO will decrease performance when more pixels on the screen are occluded.

 # Property Overview
Active checkBox: Toggle the SSAO effect on the final target.
Radius : The radius that ssao will sample from in perspective space.
Intensity : The amount that light is shadowed by Ambient Occlusion.
BlurDepthThreshold : A threshold of depth for when pixels should be blurred.
DebugBuffer checkBox: If on, the output light buffer will be set to the ambient occlusion for debugging.

 # World Scale and SSAO
SSAO gives the user control of the radius of the spherical sampling region.  This should be set proportional to normal sized objects in the scene.  The player is usually a good object to model the SSAO radius with.  Make the radius too small for the character, and the ambient occlusion effect will be weak.  Make the radius too large however, and other far away objects will start to cast shadows on your character model.  The properties of SSAO are constant across the entire scene, so one should experiment with Radius  to get the desired ambient occlusion effect.

 # Ambient Occlusion Intensity
While the Intensity  property has a direct influence on the shadow introduced in SSAO, one should first choose the appropriate Radius  value.  In general, the larger the sampling radius from a fragment, the further away the sampled geometry will be, and thus the lighter it will become.  Intensity  should be used to mitigate the effect that Radius  has on the ambient occlusion.



![SSAO_RadiusVsIntensity](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/48206.gif)


 # Blur Depth
SSAO can introduce artifacts, so the ambient occlusion layer is blurred.  To see why this is important, observe the following image with no blurring:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28587.png) *No BlurDepthThreshold *


Horizontal patterns become noticeable from the shadow and the sphere has repeating dots introduced in ambient occlusion.  Here is the same sphere with a large blurring threshold:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28585.png) *BlurDepthThreshold  is too high*


The artifacts are gone and the result looks far better, however the blur is too intense and has bled the AO shadow onto the surface of the sphere in an unrealistic way.  To avoid this, the blur should only occur at small changes in depth, which is determined by BlurDepthThreshold .  There's a fine range of thresholds that are large enough to avoid horizontal patterns, and small enough to avoid separating the shadow from the object.  A correct depth value can produce the following result:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28583.png) *BlurDepthThreshold  is just right*


 # Related Material
 ## Manual
- [Deferred and Forward Renderer](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown) 

 