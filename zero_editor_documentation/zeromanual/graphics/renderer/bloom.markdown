Bloom is a collection of PostProcess RenderTasks that adds an emissive effect to bright pixels.

 # Theory
Bloom comes from the idea that the no lens, such as an eye or a camera, can distinguish perfectly between adjacent incoming light rays of high intensity.  The light that passes through will be scattered, causing the color of some surfaces to bleed past it's boundary.  Under normal circumstances, this effect is invisible, but with large intensity the scattering becomes noticeable.  This is what's known as bloom.

(WARNING)**Performance Impact** Bloom will decrease performance because of the extra render passes made to upsample and downsample.  The only way to increase performance is to remove the component.

 # Property Overview
Active checkBox: Toggle the bloom effect on the final target.
Intensity : A scaling factor for brightness.
Threshold : The minimum brightness that bloom may be applied to.
{nav icon=check-square-o, name=Bloom1}: Apply the 1st blur and down sample pass.
{nav icon=check-square-o, name=Bloom2}: Apply the 2nd blur and down sample pass.
{nav icon=check-square-o, name=Bloom3}: Apply the 3rd blur and down sample pass.
{nav icon=check-square-o, name=Bloom4}: Apply the 4th blur and down sample pass.
{nav icon=check-square-o, name=Bloom5}: Apply the 5th blur and down sample pass.
DebugBuffer checkBox: Debug draw just the added light from the bloom passes.


## Changing Intensity

The effect of bloom on a color is controlled by two parameters, Intensity  and Threshold .  The threshold is the minimum luminance a fragment must have in order to be subject to bloom.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28603.png) *Decreasing Threshold *


NOTE: The luminance of a fragment can be determined by `Utility.luminance`.

The intensity then scales the brightness level of fragments subject to bloom.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28601.png) *Increasing Intensity *


 # Bloom Pipeline
The ability to control the effect of bloom on a color is only the first step in a applying bloom.  Once the brightness of each fragment is determined, the result is blurred and then down sampled a number of times.  Down sampling means to decrease the resolution of an image.  The process of down sampling and blurring happens 5 times.  Each result can be added or excluded from the final target using {nav icon=check-square-o, name=Bloom1} through {nav icon=check-square-o, name=Bloom5}.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28607.png) *Bloom targets incrementally added from **smallest to largest** blur radius*




![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28611.png) *Bloom targets incrementally added from **largest to smallest** blur radius*


 # Related Material
 ## Manual
- [Deferred and Forward Renderer](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown) 

 