 `Graphics`

(NOTE) Interface used to define unique render settings for a base RenderGroup and its sub RenderGroups.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddSubSettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subrendergrouppass.markdown#addsubsettings-void)| |[safeid32](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32.markdown)| |
|[ ExcludeSubRenderGroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subrendergrouppass.markdown#excludesubrendergroup-vo)| | | |
|[ Reset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subrendergrouppass.markdown#reset-void)| | | |
|[ SetDefaultSettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/subrendergrouppass.markdown#setdefaultsettings-void)| | | |


 #  Properties


---  
 #  Methods


---  
 #  AddSubSettings : Void

> Define the settings to use for a specific RenderGroup. Given RenderGroup must be a child of the base RenderGroup, or the base itself, that this was initialized with.
> |Name|Type|Description|
> |---|---|---|
> |subSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown)| |
> |subGroup|[rendergroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendergroup.markdown)| |
> |subPass|[materialblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddSubSettings(subSettings : RenderSettings, subGroup : RenderGroup, subPass : MaterialBlock)
> ``` 


---  
 #  ExcludeSubRenderGroup : Void

> Explicitely exclude a RenderGroup from rendering when there are default settings. Given RenderGroup must be a child of the base RenderGroup, or the base itself, that this was initialized with.
> |Name|Type|Description|
> |---|---|---|
> |subGroup|[rendergroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendergroup.markdown)| |
> ``` lang=cpp, name=Zilch
> function ExcludeSubRenderGroup(subGroup : RenderGroup)
> ``` 


---  
 #  Reset : Void

> Resets interface back to the initial creation state with a given base RenderGroup.
> |Name|Type|Description|
> |---|---|---|
> |baseRenderGroup|[rendergroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendergroup.markdown)| |
> ``` lang=cpp, name=Zilch
> function Reset(baseRenderGroup : RenderGroup)
> ``` 


---  
 #  SetDefaultSettings : Void

> Settings to use for the base or all sub RenderGroups that do not have specified settings. Without defaults, the base or any sub RenderGroup without settings will not render.
> |Name|Type|Description|
> |---|---|---|
> |defaultSettings|[rendersettings](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rendersettings.markdown)| |
> |defaultPass|[materialblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/materialblock.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetDefaultSettings(defaultSettings : RenderSettings, defaultPass : MaterialBlock)
> ``` 


---  
 

 