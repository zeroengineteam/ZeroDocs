 `Component` `Gameplay`



(NOTE) Manages all setup between Camera, Renderer, and viewport UI that is required to define how anything is to be rendered.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#cameraviewport-void)|[ Camera](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#camera-zero-engine-docum)|[component](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/component.markdown)| |
|[ ScreenToViewport](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#screentoviewport-zero-en)|[ CameraPath](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#camerapath-zero-engine-d)| | |
|[ ScreenToWorldPlane](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#screentoworldplane-zero)|[ FinalTexture](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#finaltexture-zero-engine)| | |
|[ ScreenToWorldRay](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#screentoworldray-zero-en)|[ ForwardViewportEvents](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#forwardviewportevents-ze)| | |
|[ ScreenToWorldViewPlane](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#screentoworldviewplane-z)|[ Frustum](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#frustum-zero-engine-docu)| | |
|[ ScreenToWorldZPlane](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#screentoworldzplane-zero)|[ MarginColor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#margincolor-zero-engine)| | |
|[ ViewPlaneSize](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewplanesize-zero-engin)|[ MouseWorldRay](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#mouseworldray-zero-engin)| | |
|[ ViewportTakeFocus](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewporttakefocus-zero-e)|[ NormalizedOffset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#normalizedoffset-zero-en)| | |
|[ ViewportToScreen](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewporttoscreen-zero-en)|[ NormalizedSize](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#normalizedsize-zero-engi)| | |
|[ WorldToScreen](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#worldtoscreen-zero-engin)|[ RendererPath](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#rendererpath-zero-engine)| | |
| |[ RenderInEditor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#renderineditor-zero-engi)| | |
| |[ RenderInGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#renderingame-zero-engine)| | |
| |[ RenderOrder](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#renderorder-zero-engine)| | |
| |[ RenderToViewport](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#rendertoviewport-zero-en)| | |
| |[ ResolutionOrAspect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#resolutionoraspect-zero)| | |
| |[ ViewportHasFocus](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewporthasfocus-zero-en)| | |
| |[ ViewportOffset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewportoffset-zero-engi)| | |
| |[ ViewportOffsetWithMargin](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewportoffsetwithmargin)| | |
| |[ ViewportResolution](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewportresolution-zero)| | |
| |[ ViewportResolutionWithMargin](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewportresolutionwithma)| | |
| |[ ViewportScaling](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewportscaling-zero-eng)| | |
| |[ ViewToPerspective](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#viewtoperspective-zero-e)| | |
| |[ WorldToPerspective](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#worldtoperspective-zero)| | |
| |[ WorldToView](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cameraviewport.markdown#worldtoview-zero-engine)| | |


 #  Properties


---  
 #  Camera : [camera](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/camera.markdown)

 `read-only`

> Find the Camera component from the CameraPath (or null if it doesn't exist).
> ``` lang=cpp, name=Zilch
> var Camera : Camera


---  
 #  CameraPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cogpath.markdown)

> Object with the Camera component to be used for rendering. A Camera can only be used by one CameraViewport, if already used by another usage will be stolen when assigned.
> ``` lang=cpp, name=Zilch
> var CameraPath : CogPath


---  
 #  FinalTexture : [texture](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/texture.markdown)

 `read-only`

> Texture that contains the end result of this CameraViewport's rendering. Must be explicitly written to in renderer script.
> ``` lang=cpp, name=Zilch
> var FinalTexture : Texture


---  
 #  ForwardViewportEvents : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Forwards mouse events to viewports underneath this viewport.
> ``` lang=cpp, name=Zilch
> var ForwardViewportEvents : Boolean


---  
 #  Frustum : [frustum](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/frustum.markdown)

 `read-only`

> Creates a frustum using the CameraViewport's settings (including aspect ratio). If the Camera is null, then this will throw an exception.
> ``` lang=cpp, name=Zilch
> var Frustum : Frustum


---  
 #  MarginColor : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

> Color to used for letterbox/scaling margins.
> ``` lang=cpp, name=Zilch
> var MarginColor : Real4


---  
 #  MouseWorldRay : [ray](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown)

 `read-only`

> Get the world ray starting from the mouse.
> ``` lang=cpp, name=Zilch
> var MouseWorldRay : Ray


---  
 #  NormalizedOffset : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Offset of the viewport in normalized UI coordinates.
> ``` lang=cpp, name=Zilch
> var NormalizedOffset : Real2


---  
 #  NormalizedSize : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Size of viewport in normalized UI coordinates.
> ``` lang=cpp, name=Zilch
> var NormalizedSize : Real2


---  
 #  RendererPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cogpath.markdown)

> Object with renderer script that connects to RenderTasksUpdate that determines what rendering will be done.
> ``` lang=cpp, name=Zilch
> var RendererPath : CogPath


---  
 #  RenderInEditor : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If rendering will be ran in edit mode.
> ``` lang=cpp, name=Zilch
> var RenderInEditor : Boolean


---  
 #  RenderInGame : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If rendering will be ran in play game mode.
> ``` lang=cpp, name=Zilch
> var RenderInGame : Boolean


---  
 #  RenderOrder : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

> The order that rendering should be done relative to other CameraViewports, lowest to highest.
> ``` lang=cpp, name=Zilch
> var RenderOrder : Integer


---  
 #  RenderToViewport : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If the rendering result in FinalTexture should also be placed on the UI viewport.
> ``` lang=cpp, name=Zilch
> var RenderToViewport : Boolean


---  
 #  ResolutionOrAspect : [integer2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer2.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ResolutionOrAspect : Integer2


---  
 #  ViewportHasFocus : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> If the viewport created by this CameraViewport, if rendering to one, has focus.
> ``` lang=cpp, name=Zilch
> var ViewportHasFocus : Boolean


---  
 #  ViewportOffset : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The current offset of the viewport, in pixels.
> ``` lang=cpp, name=Zilch
> var ViewportOffset : Real2


---  
 #  ViewportOffsetWithMargin : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The current offset of the viewport's margin, in pixels.
> ``` lang=cpp, name=Zilch
> var ViewportOffsetWithMargin : Real2


---  
 #  ViewportResolution : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The current resolution of the viewport.
> ``` lang=cpp, name=Zilch
> var ViewportResolution : Real2


---  
 #  ViewportResolutionWithMargin : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

 `read-only`

> The current resolution of the viewport including margin.
> ``` lang=cpp, name=Zilch
> var ViewportResolutionWithMargin : Real2


---  
 #  ViewportScaling : [ViewportScaling](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#viewportscaling)

> Method to use for sizing the viewport.
> ``` lang=cpp, name=Zilch
> var ViewportScaling : ViewportScaling


---  
 #  ViewToPerspective : [real4x4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4x4.markdown)

 `read-only`

> Transformation that defines how the view frustum is mapped to normalized coordinates, pre W divide.
> ``` lang=cpp, name=Zilch
> var ViewToPerspective : Real4x4


---  
 #  WorldToPerspective : [real4x4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4x4.markdown)

 `read-only`

> Concatenation of the WorldToView and ViewToPerspective transformations.
> ``` lang=cpp, name=Zilch
> var WorldToPerspective : Real4x4


---  
 #  WorldToView : [real4x4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4x4.markdown)

 `read-only`

> Transformation that defines view space as the Camera at the origin and the view direction as -Z.
> ``` lang=cpp, name=Zilch
> var WorldToView : Real4x4


---  
 #  Methods


---  
 #  CameraViewport : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CameraViewport()
> ``` 


---  
 #  ScreenToViewport : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Convert a screen point to a point relative to the viewport.
> |Name|Type|Description|
> |---|---|---|
> |screenPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function ScreenToViewport(screenPoint : Real2) : Real2
> ``` 


---  
 #  ScreenToWorldPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> Convert the screen point to a position on a given plane.
> |Name|Type|Description|
> |---|---|---|
> |screenPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |worldPlaneNormal|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |worldPlanePosition|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function ScreenToWorldPlane(screenPoint : Real2, worldPlaneNormal : Real3, worldPlanePosition : Real3) : Real3
> ``` 


---  
 #  ScreenToWorldRay : [ray](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown)

> Convert a screen point to a ray.
> |Name|Type|Description|
> |---|---|---|
> |screenPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function ScreenToWorldRay(screenPoint : Real2) : Ray
> ``` 


---  
 #  ScreenToWorldViewPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> Convert the screen point to a position on the view plane at a given depth.
> |Name|Type|Description|
> |---|---|---|
> |screenPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |viewDepth|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ScreenToWorldViewPlane(screenPoint : Real2, viewDepth : Real) : Real3
> ``` 


---  
 #  ScreenToWorldZPlane : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> Convert the screen point to a position on the z plane at a given depth.
> |Name|Type|Description|
> |---|---|---|
> |screenPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |worldDepth|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ScreenToWorldZPlane(screenPoint : Real2, worldDepth : Real) : Real3
> ``` 


---  
 #  ViewPlaneSize : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Size of the screen at a Depth.
> |Name|Type|Description|
> |---|---|---|
> |viewDepth|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function ViewPlaneSize(viewDepth : Real) : Real2
> ``` 


---  
 #  ViewportTakeFocus : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Returns whether or not it succeeded in taking focus. Will always fail if RenderToViewport is false.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ViewportTakeFocus() : Boolean
> ``` 


---  
 #  ViewportToScreen : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Convert a viewport point to a screen point.
> |Name|Type|Description|
> |---|---|---|
> |viewportPoint|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function ViewportToScreen(viewportPoint : Real2) : Real2
> ``` 


---  
 #  WorldToScreen : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> Convert a world point to a screen point.
> |Name|Type|Description|
> |---|---|---|
> |worldPoint|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function WorldToScreen(worldPoint : Real3) : Real2
> ``` 


---  
 

 