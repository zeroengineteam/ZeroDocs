 `Resource` `Graphics`



(NOTE) Data that represents a texture in the way that is intended to be used by graphics hardware.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ CreateRuntime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#createruntime-zero-engin)|[ AddressingX](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#addressingx-zero-engine)|Resource| |
|[ SubUpload](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#subupload-void)|[ AddressingY](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#addressingy-zero-engine)| | |
|[ Upload](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#upload-void)|[ Anisotropy](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#anisotropy-zero-engine-d)| | |
| |[ CompareFunc](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#comparefunc-zero-engine)| | |
| |[ CompareMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#comparemode-zero-engine)| | |
| |[ Compression](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#compression-zero-engine)| | |
| |[ Filtering](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#filtering-zero-engine-do)| | |
| |[ Format](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#format-zero-engine-docum)| | |
| |[ Height](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#height-zero-engine-docum)| | |
| |[ MipMapping](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#mipmapping-zero-engine-d)| | |
| |[ Size](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#size-zero-engine-documen)| | |
| |[ Type](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#type-zero-engine-documen)| | |
| |[ Width](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown#width-zero-engine-docume)| | |


 #  Properties


---  
 #  AddressingX : [TextureAddressing](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#textureaddressing)

> How to treat uv coordinates outside of [0, 1] along the Texture's width.
> ``` lang=cpp, name=Zilch
> var AddressingX : TextureAddressing


---  
 #  AddressingY : [TextureAddressing](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#textureaddressing)

> How to treat uv coordinates outside of [0, 1] along the Texture's height.
> ``` lang=cpp, name=Zilch
> var AddressingY : TextureAddressing


---  
 #  Anisotropy : [TextureAnisotropy](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#textureanisotropy)

> Max ratio of anisotropy that filtering will account for at oblique viewing angles.
> ``` lang=cpp, name=Zilch
> var Anisotropy : TextureAnisotropy


---  
 #  CompareFunc : [TextureCompareFunc](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturecomparefunc)

> Which method of comparison should be used if CompareMode is set to Enable.
> ``` lang=cpp, name=Zilch
> var CompareFunc : TextureCompareFunc


---  
 #  CompareMode : [TextureCompareMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturecomparemode)

> If sampling in hardware should perform comparison instead of fetching. Requires using SamplerShadow2d in the shader.
> ``` lang=cpp, name=Zilch
> var CompareMode : TextureCompareMode


---  
 #  Compression : [TextureCompression](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturecompression)

 `read-only`

> Block compression method being used. Requires pre-processing, cannot be set for runtime Textures.
> ``` lang=cpp, name=Zilch
> var Compression : TextureCompression


---  
 #  Filtering : [TextureFiltering](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturefiltering)

> How samples should be blended under minification/magnification.
> ``` lang=cpp, name=Zilch
> var Filtering : TextureFiltering


---  
 #  Format : [TextureFormat](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#textureformat)

 `read-only`

> Memory format of the stored pixel data. Set on Upload() for runtime Textures.
> ``` lang=cpp, name=Zilch
> var Format : TextureFormat


---  
 #  Height : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Height of the Texture in pixels. Set on Upload() for runtime Textures.
> ``` lang=cpp, name=Zilch
> var Height : Integer


---  
 #  MipMapping : [TextureMipMapping](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturemipmapping)

> If downsampled versions of the texture (mip maps) should be generated. PreGenerated is not valid for runtime Textures.
> ``` lang=cpp, name=Zilch
> var MipMapping : TextureMipMapping


---  
 #  Size : [integer2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer2.markdown)

 `read-only`

> Width and height (x, y) of the Texture in pixels. Set on Upload() for runtime Textures.
> ``` lang=cpp, name=Zilch
> var Size : Integer2


---  
 #  Type : [TextureType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturetype)

 `read-only`

> The type of texture data being represented.
> ``` lang=cpp, name=Zilch
> var Type : TextureType


---  
 #  Width : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Width of the Texture in pixels. Set on Upload() for runtime Textures.
> ``` lang=cpp, name=Zilch
> var Width : Integer


---  
 #  Methods


---  
 #  CreateRuntime : [texture](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown)

 `static`

> Makes an anonymous Texture resource that can be defined by script and uploaded to the gpu.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateRuntime() : Texture
> ``` 


---  
 #  SubUpload : Void

> Uploads the given texture data, overwriting a sub region of the texture data that is already on the gpu.
> |Name|Type|Description|
> |---|---|---|
> |textureData|[texturedata](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texturedata.markdown)| |
> |xOffset|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |yOffset|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function SubUpload(textureData : TextureData, xOffset : Integer, yOffset : Integer)
> ``` 


---  
 #  Upload : Void

> Uploads the given texture data to the gpu, configured with the current settings of this Texture.
> |Name|Type|Description|
> |---|---|---|
> |textureData|[texturedata](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texturedata.markdown)| |
> ``` lang=cpp, name=Zilch
> function Upload(textureData : TextureData)
> ``` 


---  
 

 