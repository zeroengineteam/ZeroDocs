 `Graphics`

(NOTE) Contains all output targets and render settings needed for a render task.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#rendersettings-void)|[ BlendSettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#blendsettings-zero-engin)| | |
| |[ ColorTarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#colortarget-zero-engine)| | |
| |[ CullMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#cullmode-zero-engine-doc)| | |
| |[ DepthSettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#depthsettings-zero-engin)| | |
| |[ DepthTarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#depthtarget-zero-engine)| | |
| |[ GlobalShaderInputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#globalshaderinputs-zero)| | |
| |[ MultiRenderTarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown#multirendertarget-zero-e)| | |


 #  Properties


---  
 #  BlendSettings : [blendsettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/blendsettings.markdown)

> Settings to use when blending shader output with the ColorTarget, implicitly BlendSettings0.
> ``` lang=cpp, name=Zilch
> var BlendSettings : BlendSettings


---  
 #  ColorTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendertarget.markdown)

> The RenderTarget of a color format to output to, implicitly RenderTarget0.
> ``` lang=cpp, name=Zilch
> var ColorTarget : RenderTarget


---  
 #  CullMode : [CullMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#cullmode)

> 
> ``` lang=cpp, name=Zilch
> var CullMode : CullMode


---  
 #  DepthSettings : [depthsettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/depthsettings.markdown)

> Settings to use when doing depth/stencil testing with DepthTarget.
> ``` lang=cpp, name=Zilch
> var DepthSettings : DepthSettings


---  
 #  DepthTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendertarget.markdown)

> The RenderTarget of a depth format to use as a depth buffer for depth/stencil testing.
> ``` lang=cpp, name=Zilch
> var DepthTarget : RenderTarget


---  
 #  GlobalShaderInputs : [shaderinputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/shaderinputs.markdown)

> Shader input values to be globally overridden for all objects/shaders.
> ``` lang=cpp, name=Zilch
> var GlobalShaderInputs : ShaderInputs


---  
 #  MultiRenderTarget : [multirendertarget](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multirendertarget.markdown)

 `read-only`

> Interface for configuring multiple color target outputs.
> ``` lang=cpp, name=Zilch
> var MultiRenderTarget : MultiRenderTarget


---  
 #  Methods


---  
 #  RenderSettings : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RenderSettings()
> ``` 


---  
 #  RenderSettings : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ||[rendersettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown)| |
> ``` lang=cpp, name=Zilch
> function RenderSettings( : RenderSettings)
> ``` 


---  
 

 