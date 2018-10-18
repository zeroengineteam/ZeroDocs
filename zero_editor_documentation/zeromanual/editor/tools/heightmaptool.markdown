The HeightMapTool is a tool used to create a [HeightMap](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/HeightMap.markdown) object and manipulate patches created on it. It has five sub-tools the user can use to create and destroy, raise and lower, smooth and sharpen, flatten, and paint patches on a HeightMap object.

 # Using the HeightMapTool
There are two ways to access the HeightMapTool:

 - Select `HeightMapTool` from SelectTool drop-down menu in the `Tools Window`
 - Or, press `7`, the hotkey for bringing up the HeightMapTool

When the HeightMapTool is opened and there is no previous HeightMap object, a message will appear on the screen informing the user that there is no HeightMap object, as can be seen here:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47435.png)


To make a new HeightMap object, simply click anywhere on the text that has appeared on the Level window. An object named `HeightMap` should now appear in the Objects Window.

Now that there is a HeightMap object, the user may start adding patches to it by using the CreateDestroy sub-tool found in CreateTool drop-down menu within HeightMapTool. Patches are the segments of the HeightMap that can be altered through the HeightMapTool.

 ## CreateDestroy
The CreateDestroy sub-tool is used to create and destroy patches that make up the height map. The size of the patch is created is dictated by the UnitsPerPatch  property of the HeightMap object. See the [[ for more information on this important property.

There are four properties in the CreateDestroyTool window that define certain parameters of the patches created:

 - BaseHeight  - A real that defines the height at which the map will be created

 - UsePerlinNoise checkBox - A boolean that when sets to true allows the user to create patches with different levels of noise, defined by PerlinFrequency  and PerlinAmplitude .

 - PerlinFrequency  - A Real that defines the frequency of "bumps" to be added to the patch (e.g., a higher number makes for a bumpier patch)

 - PerlinAmplitude  - A Real that defines the height of the "bumps" created (e.g., a higher number makes for higher bumps)

To create a new patch, simply click wherever in the Level Window where the patch should be placed. To destroy a patch, `Shift + Click` on the patch to be destroyed.


![ca042b25-6da8-4d65-aa2b-020b689b0b9b](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47437.gif)


Settings are changed on a per-patch basis and do not affect previously placed patches (notice the PerlinFrequency  and PerlinAmplitude  have been modified:



![6d029a7e-3104-45f6-9830-6b1412f94170](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47441.gif)


 ## RaiseLower
The RaiseLower sub-tool is used to increase and decrease points on the height map patches. There are four properties in the RaiseLowerTool window that define the range and strength of the area to be raised or lowered:

 - Radius  - A Real that defines the size of the area (in the shape of a circle) to be raised or lowered according to the value set in the property `Strength`.

 - FeatherRadius  - A Real that defines a circle outside the one created by the Radius property, where the value of the property `Strength` linearly interpolates down from 100% (where it meets the inner circle) to 0% (at its own outer limit).

 - Strength  - A Real that defines the strength by which a part of the height map (see Radius and FeatherRadius) is raised or lowered.

 - {"nav icon=check-square-o, name=Relative} - This property is not currently functional.

To raise an area on a patch of the height map, simply left-click on the area to be raised. One can either make multiple clicks or keep the left-mouse button held while moving the mouse around to continue to raise parts of the patch. To lower an area on a patch, hold Shift while clicking.



![fd487041-37d1-4506-a528-365c619855d8](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47469.gif) 


NOTE:
 A number of sub-tools in the HeightMapTool have both Radius  and FeatherRadius . These two properties work together with Strength  to determine the values by which the height map is being changed. While the descriptions of these properties in the property lists of the sub-tools is accurate, a diagram is provided to make clear how the value changes from the circle defined by Radius  and the circle defined by FeatherRadius :
 ![radiusfeatherradius](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1036.png)

 ## SmoothSharpen
The SmoothSharpen sub-tool is used to either smooth or sharpen bumps on the height map. There are seven properties in the SmoothSharpenTool window that define the range, strength, and sampling used to smooth and sharpen the map:

 - Radius  - A real that defines the size of the area (in the shape of a circle) to be smoothed or sharpened according to the value set in the property Strength .

 - FeatherRadius  - A real that defines the area outside the area defined by `Radius`, where the value of the property `Strength` linearly interpolates down from 100% (where it meets the inner circle) to 0% (at its own outer limit).

 - Strength  - A Real that defines the strength by which a part of the height map (see Radius and FeatherRadius) is smoothed or sharpened.

(IMPORTANT)**Deprecated Properties** While the following properties will affect the behavior of the SmoothSharpen tool, it is highly recommended that the user leaves them at their default values as they will be removed in a later build.
 UniformSamples , RandomSamples , RandomSampleDistance , and
 AutoDetermineSamples 

To smooth an area on the height map, simply left-click on the area to be smoothed. One can either make multiple clicks or keep the left-mouse button held while moving the mouse around to continue smoothing parts of the patch. To sharpen an area on a patch, hold `Shift` while clicking (or holding the left-mouse button). 

The following screenshot shows two patches; the one on the left has been smoothed, while the one on the right has been sharpened:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47480.png)


 ## Flatten
The flatten sub-tool is used to to flatten an area of a patch to a certain height. By default, this height will be sampled on the first mouse-click when using the sub-tool. This allows the user to pick an area on the height map with the desired height and then flatten the surroundings to match that height. To flatten based on a specific height instead of a sample, set SampleOnMouseDown checkBox to `false`. The properties of the Flatten tool are as follows:

 - Radius  - A real that defines the size of the area (in the shape of a circle) to be flattened according to a sample or the value set in the property Height .

 - FeatherRadius  - A real that defines the area outside the area defined by Radius , where the value of the property Height  linearly interpolates down from 100% (where it meets the inner circle) to 0% (at its own outer limit).

 - Height  - A real that defines the specific height to which one wishes to flatten a given part of the height map (set this value if not sampling from the mouse-click).

 - SampleOnMouseDown checkBox - A boolean that when checked, samples the height to which the map will be flattened. If unchecked, specify the height in Height .

(IMPORTANT)**Deprecated Properties**
 SlopeNormal , SampleNormal 

To flatten an area on the height map, one must first decide whether to sample a height from a surrounding point on the height map or to set the value directly in Height . Once a method has been chosen, simply left-click (or hold the left-mouse button) on the area to be flattened.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47481.png) *A flattened "valley" amidst raised peaks on a height map*


 ## WeightPainter
The WeightPainter sub-tool is used to paint textures onto a height map. In order to use the WeightPainter sub-tool, one must first make a  [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials.markdown)  that has the  [HeightMapTextureWeights](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/HeightMapTextureWeights.markdown)  material block on it, as seen here:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47485.png)


Both the `HeightMapTextureWeights` material block and the WeightPainter sub-tool support four separate textures. The user must load each texture into the `HeightMapTextureWeights` material block.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47487.png)


Once this new [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials.markdown) has been applied to the [HeightMap](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/heightmap.markdown) object, one may use the WeightPainter sub-tool to select each texture separately and paint the height map with it. TextureChannel enum on the WeightPainter sub-tool gives the user access to each of the four [Textures](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown). The following screenshots show a height map--the one created in the Material has been applied to the HeightMap object, one may use the WeightPainter sub-tool to select each texture separately and paint the height map with it. The following screenshot shows a height map, the one created above, painted with varying texture weights. The *road* is 100% of `Texture3` and `Texture4`, while the rest is all `Texture1` with splotches of the other textures painted with a low strength.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47490.png)


*All four weighted textures used with varying weights.*



 # Related Materials
 ## Manual
- [HeightMap Collider](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collision/heightmapcollider.markdown)

 ## Code Reference
- [HeightMap](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/HeightMap.markdown) 
- [Integer](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/zilch_base_types/Integer.markdown) 
- [Real](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/zilch_base_types/Real.markdown) 
- [Boolean](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/zilch_base_types/Boolean.markdown) 
- [Real3](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/zilch_base_types/Real3.markdown) 
- [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/Material.markdown) 

 

 