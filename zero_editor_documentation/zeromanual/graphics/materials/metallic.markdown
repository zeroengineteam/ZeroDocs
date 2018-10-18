The metallic fragment, in the form of either a map or value, describes whether a [Material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/materials.markdown), or part of a material, should have the properties of a metal (or conductor) in relation to light. Metals have high specular and their color represents the visible spectrum of light that a particular metal reflects. This is in opposition for dielectrics, or non-metals, that--for the most part--have high diffuse reflectance. In fact, when authoring a new material for a PBR-based renderer, whether that material is a metal or not (or some combination of the two) is usually the first consideration one should make.

As metals have very high specular and very low diffuse reflectance, their color comes from a "tint" to reflected light. Gold and copper are two metals associated with their unique colors, instead of the grays usually found with metals. A simplified explanation of why gold and copper have the tint that they do is because they do not reflect much of the blue part of the spectrum. Compare the following three spheres, each tinted to represent gold, copper, and silver respectively.



![Metallic_Overview_Spheres](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28444.png)


Using either a map or a value fragment, one may assign a metallic value between `0.0` and `1.0`. While there may be an impulse to assign this value somewhere in the middle, it usually far more accurate to make a material or part of a material either completely `1.0` (metal) or completely `0.0` (non-metal). If the effect desired is a brushed or aged metal, this may best be achieved by using a RoughnessMap in conjunction with a MetallicMap. 

 #  The Metallic Fragment

Metallic may be set using a [Texture](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/texture.markdown) map or a value. If a value is used, it applied uniformly across the entire Material. If a map is used, the metallic value may be set to different levels across the Material.  If there is neither a metallic map or value fragment, it would be as if a metallic value of `0.0` is applied to the entire Material.

 ##  MetallicValue

When a MetallicValue fragment is applied to a Material, the user may set a metallic value to applied uniformly across the Material in the from `0.0` to `1.0`. To add a MetallicValue fragment, click on the `Add MaterialBlock` button and select `MetallicValue`, as seen below:



![AddValue](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47838.gif)


The following screenshots show the progression of the metallic value of a material from `0.0` to `1.0` with a constant roughness value (`0.25`) and albedo value (gold, copper, and silver, front to back):



![MetalTriA](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28438.png) ![MetalTriB](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28440.png) ![MetalTriC](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/28442.png)


The spheres furthest to the left look have a matte look there as there is no metallic or specular reflectance added while the spheres furthest to the right looks like polished, completely reflective metals. The difference between the three sphere in the middle of each line are subtle and may not be terribly useful, but with a uniform metallic value that shouldn't be a problem. The vast majority of objects are either metals or non-metals so to have a uniform metallic value somewhere in between `0.0` and `1.0`, especially as the value approaches `0.5`, will not appear like the surface of anything in reality.

 ##  MetallicMap

A MetallicMap is a texture provided by an artist for use on a model. While most of these textures will be unique to the model for which they were made, others, such as tileable textures, may be applied to the materials on a number of geometric primitives while still appearing completely natural. To apply a MetallicMap fragment to a material, click on the `Add ZilchFragment` button in the Properties window:



![AddMap](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47848.gif)


A MetallicMap fragment is appropriate to use when the Material will have sections that are metallic and sections that are not. 

 # Related Materials

 ## Manual
- [materials](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/materials.markdown)
- [adding_textures_and_sprites](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown)

 ## Code Reference
- [material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/material.markdown)
- [texture](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/texture.markdown) 
  
  
  
  
  
  
  

 