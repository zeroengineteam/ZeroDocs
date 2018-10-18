 `Graphics`

(NOTE) Vertex data and attribute semantics for defining data that can be uploaded to the gpu.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddAttribute](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#addattribute-void)|[ VertexCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#vertexcount-zero-engine)|[safeid32](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/safeid32.markdown)| |
|[ AddByte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#addbyte-void)| | | |
|[ AddReal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#addreal-void)| | | |
|[ AddShort](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#addshort-void)| | | |
|[ ClearAttributes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#clearattributes-void)| | | |
|[ ClearData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#cleardata-void)| | | |
|[ GetAttributes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#getattributes-zero-engin)| | | |
|[ GetElementCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#getelementcount-zero-eng)| | | |
|[ GetElementType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#getelementtype-zero-engi)| | | |
|[ GetVertexData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#getvertexdata-zero-engin)| | | |
|[ IsValidVertexData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexbuffer.markdown#isvalidvertexdata-zero-e)| | | |


 #  Properties


---  
 #  VertexCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns the number of vertices that have a complete set of data stored.
> ``` lang=cpp, name=Zilch
> var VertexCount : Integer


---  
 #  Methods


---  
 #  AddAttribute : Void

> Adds an attribute to the definition of the vertices that are to be stored. Add the attributes in the order that they should be stored in memory on a vertex.
> |Name|Type|Description|
> |---|---|---|
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> |elementType|[VertexElementType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexelementtype)| |
> |elementCount|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddAttribute(semantic : VertexSemantic, elementType : VertexElementType, elementCount : Integer)
> ``` 


---  
 #  AddByte : Void

> Adds data as bytes to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddByte(value : Integer)
> ``` 


---  
 #  AddByte : Void

> Adds data as bytes to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddByte( : Integer2)
> ``` 


---  
 #  AddByte : Void

> Adds data as bytes to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer3.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddByte( : Integer3)
> ``` 


---  
 #  AddByte : Void

> Adds data as bytes to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer4.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddByte( : Integer4)
> ``` 


---  
 #  AddReal : Void

> Adds data as floats to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddReal(value : Real)
> ``` 


---  
 #  AddReal : Void

> Adds data as floats to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddReal(value : Real2)
> ``` 


---  
 #  AddReal : Void

> Adds data as floats to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddReal(value : Real3)
> ``` 


---  
 #  AddReal : Void

> Adds data as floats to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddReal(value : Real4)
> ``` 


---  
 #  AddShort : Void

> Adds data as shorts to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> |value|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddShort(value : Integer)
> ``` 


---  
 #  AddShort : Void

> Adds data as shorts to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddShort( : Integer2)
> ``` 


---  
 #  AddShort : Void

> Adds data as shorts to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer3.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddShort( : Integer3)
> ``` 


---  
 #  AddShort : Void

> Adds data as shorts to the buffer, data is expected in the order of the attributes, one vertex after another.
> |Name|Type|Description|
> |---|---|---|
> ||[integer4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer4.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddShort( : Integer4)
> ``` 


---  
 #  ClearAttributes : Void

> Clears all added attributes from the vertex definition so they can be redefined.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearAttributes()
> ``` 


---  
 #  ClearData : Void

> Clears all added vertex data so new data can be added.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearData()
> ``` 


---  
 #  GetAttributes : [vertexsemanticrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vertexsemanticrange.markdown)

> Returns a range of attribute semantics in the order that they were added.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GetAttributes() : VertexSemanticRange
> ``` 


---  
 #  GetElementCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> Returns the number of elements stored for the given attribute, throws exception if the attribute is not in the vertex definition.
> |Name|Type|Description|
> |---|---|---|
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> ``` lang=cpp, name=Zilch
> function GetElementCount(semantic : VertexSemantic) : Integer
> ``` 


---  
 #  GetElementType : [VertexElementType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexelementtype)

> Returns the type that is used to store the given attribute, throws exception if the attribute is not in the vertex definition.
> |Name|Type|Description|
> |---|---|---|
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> ``` lang=cpp, name=Zilch
> function GetElementType(semantic : VertexSemantic) : VertexElementType
> ``` 


---  
 #  GetVertexData : [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)

> Gets the data of an attribute of a vertex, returns values of 0 if read is invalid.
> |Name|Type|Description|
> |---|---|---|
> |vertexIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> ``` lang=cpp, name=Zilch
> function GetVertexData(vertexIndex : Integer, semantic : VertexSemantic) : Real4
> ``` 


---  
 #  GetVertexData : [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)

> Gets the data of an attribute of a vertex, throws exception if attribute info doesn't match or read is invalid.
> |Name|Type|Description|
> |---|---|---|
> |vertexIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> |type|[VertexElementType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexelementtype)| |
> |count|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetVertexData(vertexIndex : Integer, semantic : VertexSemantic, type : VertexElementType, count : Integer) : Real4
> ``` 


---  
 #  IsValidVertexData : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns false if GetVertexData() would throw an exception with the same arguments.
> |Name|Type|Description|
> |---|---|---|
> |vertexIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |semantic|[VertexSemantic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexsemantic)| |
> |type|[VertexElementType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#vertexelementtype)| |
> |count|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsValidVertexData(vertexIndex : Integer, semantic : VertexSemantic, type : VertexElementType, count : Integer) : Boolean
> ``` 


---  
 

 