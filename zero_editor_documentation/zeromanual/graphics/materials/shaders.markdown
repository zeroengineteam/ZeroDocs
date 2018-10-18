Shaders may be added to Zero in the form of ZilchFragments, allowing the user to write shaders using the Zilch language. Zero currently supports the following types of shaders:

 - **Pixel** - Operates on individual pixels, setting and changing their properties.
 - **Vertex** - Operates on individual vertices, setting and changing their properties.
 - **Geometry** - Operates on transformed primitives (e.g. point, lines,  triangles), setting and changing their properties.
 - **PostProcess** - Operates on the window of an entire scene, after that scene has been processed.

When adding a new ZilchFragment, there are multiple templates for each type of shader:

| Shader | Template | Source | Description
|---|---|---
| Pixel | Pixel Annotated | P559 | All of the built-in inputs  that may be used have been commented.
| Pixel | Pixel Empty | P561 |  No inputs or outputs pre-defined.
| Pixel | Pixel Normal Map | P560 | Uses a NormalMap to perturb the surface normal
| Vertex | Vertex Annotated | P562 | All of the built-in inputs that may be used have been commented.
| Vertex | Vertex Empty | P564 | No inputs or outputs pre-defined.
| Vertex | Vertex Oscillate | P563 | Demonstration of a vertex shader that applies a simple oscillation to all vertices.
| Geometry | Point To Quad | P565 | Demonstration of generating geometry, creating quads from points.
| Geometry | Polygon Normals | P566 | Demonstration of manipulating geometry, changing normals of a triangle.
| PostProcess | Post Process Blur | P567 | Applies a simple post-process blur effect.
| PostProcess | Post Process Copy | P568 | Copies a texture.


 # Shader Translation Debug Helper

This tool translates Materials—rather, the ZilchFragments that make up the Material—into different versions of the shader language GLSL.

[Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ DebugShaderTranslation](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#debugshadertranslation) will open the tool

On the left hand side of the window are properties that set the parameters that define the shaders to be be translated: CoreVertex enum, Material enum, and RenderPass enum. `Translation Language` set the version of GLSL to translate to.  These options set what exactly will be translated. Material enum, for example, sets the Material to be translated as its name would suggest.

Here's a screenshot of a dragon material made for PBR:



![Gold Dragon Material](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/88445.png) **Figure 1**: A material to apply to a dragon material made with PBR in mind.


Figure 1 shows that the [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown) has Material Blocks for the four inputs expected by the physically-based renderer as well as a [NormalMap](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials/normal_map.markdown). When setting the Material enum to the Golden Dragon material and and set LightPass enum the shader outputs are:



![Gold Dragon Light Pass](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/88447.png)


If not familiar with GLSL, these will become overwhelmingly complex very quickly. With at least an intermediate amount of experience in GLSL, however, this translator provides a valuable tool for debugging your ZilchFragment shaders. Changing the other attributes to different settings will result in different outputs, so try to make sure that the attributes selected line up to the location on the render pipeline.

 # Related Materials
 ## Manual
- [normal_map](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials/normal_map.markdown)
- [Material](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown)
 

 