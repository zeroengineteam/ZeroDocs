A point light is a light that has a defined shape, exists at particular point in space, and sends light out equally from all points on that shape. It uses a sphere [mesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/mesh.markdown) to define its volume, as can be seen on the [Model component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/models/model_component.markdown). The light that is emitted will only be processed on geometry that the light overlaps, which is found using a special depth test unique to the point light.

 # LightIntensity and LightRadius

LightIntensity  falls off as the distance increases from the surface of the light as defined by the LightRadius . The fall off follows the inverse square law. The LightIntensity  and FalloffRadius  are independent from each other. 

LightRadius  defines the size of the "physical" object that represents the object emitting the light. This "physical" object that can only be seen in the reflection of the PointLight (see screenshots below) As this radius approaches zero, it comes to represent an infinitely small point. As the radius increases and the intensity stays the same, the light emitted will be spread out as the same intensity must now be spread across the surface of a larger object. The following series of screenshots shows a point light in the Editor view where LightIntensity  remains constant at `50`, but LightRadius  changes to values of  `0.0`, `0.5`, and `1.0`, respectively:



![Radius0](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46605.png) ![Radius0_5](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46613.png) ![Radius1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46609.png)


As is illustrated in the screenshots above, when the value LightRadius  increases, the size of the specular, or reflected, light grows. This is most obvious when looking at the reflection of the light source: the sphere reflected on the surface of the floor and wall objects gets larger. As the specular light increases, however, the intensity also dims, as the amount of energy emitted remains the same despite increasing the area from which it is emitted.

 # FalloffRadius

FalloffRadius  defines the size of the sphere mesh that acts as the volume in which emitted light may be processed. If the value defines a volume larger than what the emitted light would reach, increasing it any further will have no effect. If the value defines a volume below what the emitted light would reach, the intensity falloff is truncated. The following series of screenshots show a point light in Editor view where the value of FalloffRadius  is set to `10`, `7`, and `5`, respectively:



![Falloff10](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46617.png) ![Falloff7](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46619.png) ![Falloff5](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46623.png)


 # Related Materials
 ## Manual
- [Model component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/models/model_component.markdown)

 ## Code Reference
- [Mesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/mesh.markdown) 
  
  
  
  
  
  
  

 