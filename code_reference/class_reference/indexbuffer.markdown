 `Graphics`

(NOTE) Indices used to define non-sequential primitive construction from vertices, such as shared vertices.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Add](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/indexbuffer.markdown#add-void)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/indexbuffer.markdown#count-zero-engine-docume)|[safeid32](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/safeid32.markdown)| |
|[ Clear](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/indexbuffer.markdown#clear-void)| | | |
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/indexbuffer.markdown#get-zero-engine-document)| | | |


 #  Properties


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Number of vertex indices currently in buffer. Can be set manually to invoke vertex shading that number of times, with or without vertex data.
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  Methods


---  
 #  Add : Void

> Add a vertex index to the buffer.
> |Name|Type|Description|
> |---|---|---|
> |value|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Add(value : Integer)
> ``` 


---  
 #  Clear : Void

> Clears all stored indices so that new ones can be added.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 #  Get : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Returns the vertex index that is stored at the given index of this buffer.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(index : Integer) : Integer
> ``` 


---  
 
  
  
  
  
  
  
  

 