 `Graphics`

(NOTE) Used when requesting a RenderTarget to configure how its texture is sampled.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#samplersettings-void)|[ AddressingX](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#addressingx-zero-engine)| | |
| |[ AddressingY](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#addressingy-zero-engine)| | |
| |[ CompareFunc](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#comparefunc-zero-engine)| | |
| |[ CompareMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#comparemode-zero-engine)| | |
| |[ Filtering](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown#filtering-zero-engine-do)| | |


 #  Properties


---  
 #  AddressingX : [TextureAddressing](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureaddressing)

> How to treat uv coordinates outside of [0, 1] along the Texture's width.
> ``` lang=cpp, name=Zilch
> var AddressingX : TextureAddressing


---  
 #  AddressingY : [TextureAddressing](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureaddressing)

> How to treat uv coordinates outside of [0, 1] along the Texture's height.
> ``` lang=cpp, name=Zilch
> var AddressingY : TextureAddressing


---  
 #  CompareFunc : [TextureCompareFunc](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#texturecomparefunc)

> Which method of comparison should be used if CompareMode is set to Enable.
> ``` lang=cpp, name=Zilch
> var CompareFunc : TextureCompareFunc


---  
 #  CompareMode : [TextureCompareMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#texturecomparemode)

> If sampling in hardware should perform comparison instead of fetching. Requires using SamplerShadow2d in the shader.
> ``` lang=cpp, name=Zilch
> var CompareMode : TextureCompareMode


---  
 #  Filtering : [TextureFiltering](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#texturefiltering)

> How samples should be blended under minification/magnification.
> ``` lang=cpp, name=Zilch
> var Filtering : TextureFiltering


---  
 #  Methods


---  
 #  SamplerSettings : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SamplerSettings()
> ``` 


---  
 

 