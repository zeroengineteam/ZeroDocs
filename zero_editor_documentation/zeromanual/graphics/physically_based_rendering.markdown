Physically-based rendering (PBR) is a relatively recent rendering technique and workflow that aims to better represent how the surface of objects appear as they do in real life. This is primarily achieved by taking a more nuanced approach to how light interacts with different types of surfaces, metals and non-metals in particular. If you are unfamiliar with PBR, check out one of the following links regarding basic theory, asset creation, or the actual physics and math behind the calculations.

 # PBR Introductions and Overviews

 ## Introduction for the Artist or Designer

 - [Basic Theory of Physically Based Rendering](https://www.marmoset.co/posts/basic-theory-of-physically-based-rendering/) by Jeff Russell
 - [The Comprehensive PBR Guide - Volume I by allegorithmic](https://www.allegorithmic.com/system/files/software/download/build/PBR_Guide_Vol.1.pdf/) The Theory of Physically Based Rendering

 ## Asset Creation Guides

 - [The Comprehensive PBR Guide - Volume II by allegorithmic](https://www.allegorithmic.com/system/files/software/download/build/PBR_volume_02_rev05.pdf/) Practical Guidelines for PBR Texturing
 - [Physically-Based Rendering and You Can Too](https://www.marmoset.co/posts/physically-based-rendering-and-you-can-too/) by Joe "Earthquake" Wilson
 - [PBR Texture Conversion](https://www.marmoset.co/posts/pbr-texture-conversion/) by Joe "Earthquake" Wilson

 ## Math and Physics for the Developer

 - [Real Shading in Unreal Engine 4](http://blog.selfshadow.com/publications/s2013-shading-course/karis/s2013_pbs_epic_notes_v2.pdf) by Brian Karis
 - [Physics and Math of Shading](http://blog.selfshadow.com/publications/s2013-shading-course/hoffman/s2013_pbs_physics_math_notes.pdf/) by Naty Hoffman
 - [Physically Based Shading at Disney](http://blog.selfshadow.com/publications/s2012-shading-course/burley/s2012_pbs_disney_brdf_notes_v3.pdf/) by Brent Burley

 # Implementation in Zero

The [DeferredRenderer and ForwardRenderer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown) follow a metallic-roughness workflow (as opposed to metallic-glossiness) and expects inputs for albedo (referred to as "base color" in other workflows), metallic, roughness, and specular in the form of texture maps or uniform values. These maps or values are set via ZilchFragments and applied to a [Material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown). 

 # Related Materials
 ## Manual

- [DeferredRenderer and ForwardRenderer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/renderer/deferred_renderer.markdown)
- [Material](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/materials/materials_overview.markdown) 
  
  
  
  
  
  
  

 