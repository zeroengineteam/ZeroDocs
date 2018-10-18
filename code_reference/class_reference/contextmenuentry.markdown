 `Widget`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddCommandByName](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#addcommandbyname-zero-en)|[ Icon](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#icon-zero-engine-documen)|[safeid32eventobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32eventobject.markdown)|[contextmenuentrycommand](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentrycommand.markdown)|
|[ AddDivider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#adddivider-zero-engine-d)|[ Name](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#name-zero-engine-documen)| |[contextmenuentrydivider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentrydivider.markdown)|
|[ AddEntry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#addentry-zero-engine-doc)| | |[contextmenuentrymenu](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentrymenu.markdown)|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#contextmenuentry-void)| | | |
|[ Entries](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#entries-zero-engine-docu)| | | |
|[ GetEntry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#getentry-zero-engine-doc)| | | |
|[ RemoveEntry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown#removeentry-void)| | | |


 #  Properties


---  
 #  Icon : [string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Icon : String


---  
 #  Name : [string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  Methods


---  
 #  AddCommandByName : [contextmenuentry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |commandName|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddCommandByName(commandName : String) : ContextMenuEntry
> ``` 


---  
 #  AddDivider : [contextmenuentry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function AddDivider() : ContextMenuEntry
> ``` 


---  
 #  AddEntry : [contextmenuentry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown)

> Adds a new entry with the provided name with an icon if one is provided to this menu entries children.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddEntry(name : String) : ContextMenuEntry
> ``` 


---  
 #  ContextMenuEntry : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ContextMenuEntry()
> ``` 


---  
 #  Entries : [contextmenuentrychildrenrange](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentrychildrenrange.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Entries() : ContextMenuEntryChildrenRange
> ``` 


---  
 #  GetEntry : [contextmenuentry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/contextmenuentry.markdown)

> Returns the children entry with the provided name if it exists and null otherwise.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetEntry(name : String) : ContextMenuEntry
> ``` 


---  
 #  RemoveEntry : Void

> Remove the entry with the provided name from this menu entries children.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveEntry(name : String)
> ``` 


---  
 

 