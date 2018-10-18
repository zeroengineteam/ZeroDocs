 `Event` `Graphics`



(NOTE) Interface for adding tasks for the renderer, essentially defining a rendering pipeline.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddRenderTaskClearTarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#addrendertaskcleartarget)|[ CameraViewportCog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#cameraviewportcog-zero-e)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
|[ AddRenderTaskPostProcess](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#addrendertaskpostprocess)|[ ViewportSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#viewportsize-zero-engine)| | |
|[ AddRenderTaskRenderPass](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#addrendertaskrenderpass)| | | |
|[ AddRenderTaskSubRenderGroupPass](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#addrendertasksubrendergr)| | | |
|[ CreateSubRenderGroupPass](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#createsubrendergrouppass)| | | |
|[ GetFinalTarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#getfinaltarget-zero-engi)| | | |
|[ GetRenderTarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertasksevent.markdown#getrendertarget-zero-eng)| | | |


 #  Properties


---  
 #  CameraViewportCog : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Object with the CameraViewport component that this event is getting tasks for.
> ``` lang=cpp, name=Zilch
> var CameraViewportCog : Cog


---  
 #  ViewportSize : [integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only`

> Size of the UI viewport, or the resolution on CameraViewport if not rendering to viewport.
> ``` lang=cpp, name=Zilch
> var ViewportSize : Integer2


---  
 #  Methods


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(renderSettings : RenderSettings, color : Real4)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(renderSettings : RenderSettings, color : Real4, depth : Real)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(renderSettings : RenderSettings, color : Real4, depth : Real, stencil : Integer)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |stencilWriteMask|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(renderSettings : RenderSettings, color : Real4, depth : Real, stencil : Integer, stencilWriteMask : Integer)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(depthTarget : RenderTarget, depth : Real)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(depthTarget : RenderTarget, depth : Real, stencil : Integer)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |stencilWriteMask|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(depthTarget : RenderTarget, depth : Real, stencil : Integer, stencilWriteMask : Integer)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |colorTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(colorTarget : RenderTarget, color : Real4)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |colorTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(colorTarget : RenderTarget, depthTarget : RenderTarget, color : Real4, depth : Real)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |colorTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(colorTarget : RenderTarget, depthTarget : RenderTarget, color : Real4, depth : Real, stencil : Integer)
> ``` 


---  
 #  AddRenderTaskClearTarget : Void

> Initializes all the internal texture data for the given RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |colorTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |depthTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> |depth|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stencil|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |stencilWriteMask|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskClearTarget(colorTarget : RenderTarget, depthTarget : RenderTarget, color : Real4, depth : Real, stencil : Integer, stencilWriteMask : Integer)
> ``` 


---  
 #  AddRenderTaskPostProcess : Void

> Invokes the pixel shader for every pixel of the RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |material|[material](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/material.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskPostProcess(renderSettings : RenderSettings, material : Material)
> ``` 


---  
 #  AddRenderTaskPostProcess : Void

> Invokes the pixel shader for every pixel of the RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |postProcess|[materialblock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskPostProcess(renderSettings : RenderSettings, postProcess : MaterialBlock)
> ``` 


---  
 #  AddRenderTaskPostProcess : Void

> Invokes the pixel shader for every pixel of the RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |material|[material](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/material.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskPostProcess(renderTarget : RenderTarget, material : Material)
> ``` 


---  
 #  AddRenderTaskPostProcess : Void

> Invokes the pixel shader for every pixel of the RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderTarget|[rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)| |
> |postProcess|[materialblock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskPostProcess(renderTarget : RenderTarget, postProcess : MaterialBlock)
> ``` 


---  
 #  AddRenderTaskRenderPass : Void

> Renders a group of objects with the given settings. The RenderPass fragment defines what data is written to RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |graphicalRange|[graphicalrangeinterface](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphicalrangeinterface.markdown)| |
> |renderPass|[materialblock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskRenderPass(renderSettings : RenderSettings, graphicalRange : GraphicalRangeInterface, renderPass : MaterialBlock)
> ``` 


---  
 #  AddRenderTaskRenderPass : Void

> Renders a group of objects with the given settings. The RenderPass fragment defines what data is written to RenderTargets.
> |Name|Type|Description|
> |---|---|---|
> |renderSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendersettings.markdown)| |
> |renderGroup|[rendergroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendergroup.markdown)| |
> |renderPass|[materialblock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskRenderPass(renderSettings : RenderSettings, renderGroup : RenderGroup, renderPass : MaterialBlock)
> ``` 


---  
 #  AddRenderTaskSubRenderGroupPass : Void

> Renders all objects within a RenderGroup hierarchy, sorted in the order defined by the base RenderGroup, and can use unique render settings for each RenderGroup in the hierarchy.
> |Name|Type|Description|
> |---|---|---|
> |subRenderGroupPass|[subrendergrouppass](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/subrendergrouppass.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddRenderTaskSubRenderGroupPass(subRenderGroupPass : SubRenderGroupPass)
> ``` 


---  
 #  CreateSubRenderGroupPass : [subrendergrouppass](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/subrendergrouppass.markdown)

> Creates the interface used to define unique render settings for a base RenderGroup and its sub RenderGroups. The given RenderGroup is used to define the hierarchy, or sub hierarchy, that should be rendered. The given RenderGroup also defines the sort order for all objects that are within its hierarchy. Returned SubRenderGroupPass is only valid during this event.
> |Name|Type|Description|
> |---|---|---|
> |baseGroup|[rendergroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendergroup.markdown)| |
> ``` lang=cpp, name=Zilch
> function CreateSubRenderGroupPass(baseGroup : RenderGroup) : SubRenderGroupPass
> ``` 


---  
 #  GetFinalTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ||[TextureFormat](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureformat)| |
> ``` lang=cpp, name=Zilch
> function GetFinalTarget( : Integer2,  : TextureFormat) : RenderTarget
> ``` 


---  
 #  GetFinalTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ||[TextureFormat](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureformat)| |
> ||[samplersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetFinalTarget( : Integer2,  : TextureFormat,  : SamplerSettings) : RenderTarget
> ``` 


---  
 #  GetRenderTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)

> Returns a RenderTarget for use when adding render tasks. Target only valid during this event. Will render to the given texture instead of an internally managed texture.
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ||[TextureFormat](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureformat)| |
> ``` lang=cpp, name=Zilch
> function GetRenderTarget( : Integer2,  : TextureFormat) : RenderTarget
> ``` 


---  
 #  GetRenderTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)

> Returns a RenderTarget for use when adding render tasks. Target only valid during this event. Will render to the given texture instead of an internally managed texture.
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ||[TextureFormat](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#textureformat)| |
> ||[samplersettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/samplersettings.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetRenderTarget( : Integer2,  : TextureFormat,  : SamplerSettings) : RenderTarget
> ``` 


---  
 #  GetRenderTarget : [rendertarget](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rendertarget.markdown)

> Returns a RenderTarget for use when adding render tasks. Target only valid during this event. Will render to the given texture instead of an internally managed texture.
> |Name|Type|Description|
> |---|---|---|
> |texture|[texture](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/texture.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetRenderTarget(texture : Texture) : RenderTarget
> ``` 


---  
 

 