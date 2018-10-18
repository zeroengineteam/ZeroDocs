 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Flush](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#flush-void)|[ Capabilities](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#capabilities-zero-engine)| |[filestream](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filestream.markdown)|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#istream-void)|[ Count](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#count-zero-engine-docume)| | |
|[ Read](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#read-zero-engine-documen)|[ Position](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#position-zero-engine-doc)| | |
|[ ReadAllText](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#readalltext-zero-engine)| | | |
|[ ReadByte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#readbyte-zero-engine-doc)| | | |
|[ ReadLine](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#readline-zero-engine-doc)| | | |
|[ Seek](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#seek-zero-engine-documen)| | | |
|[ Write](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#write-zero-engine-docume)| | | |
|[ WriteByte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#writebyte-zero-engine-do)| | | |
|[ WriteText](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/istream.markdown#writetext-zero-engine-do)| | | |


 #  Properties


---  
 #  Capabilities : [StreamCapabilities](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/flags_reference.markdown#streamcapabilities)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Capabilities : StreamCapabilities


---  
 #  Count : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/doubleinteger.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Count : DoubleInteger


---  
 #  Position : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/doubleinteger.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Position : DoubleInteger


---  
 #  Methods


---  
 #  Flush : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Flush()
> ``` 


---  
 #  IStream : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IStream()
> ``` 


---  
 #  Read : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |data|Array[[byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)]| |
> |byteStart|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |byteCount|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Read(data : Array[Byte], byteStart : Integer, byteCount : Integer) : Integer
> ``` 


---  
 #  ReadAllText : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ReadAllText() : String
> ``` 


---  
 #  ReadAllText : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[iencoding](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/iencoding.markdown)| |
> ``` lang=cpp, name=Zilch
> function ReadAllText(p0 : IEncoding) : String
> ``` 


---  
 #  ReadByte : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ReadByte() : Integer
> ``` 


---  
 #  ReadLine : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ReadLine() : String
> ``` 


---  
 #  ReadLine : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[iencoding](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/iencoding.markdown)| |
> ``` lang=cpp, name=Zilch
> function ReadLine(p0 : IEncoding) : String
> ``` 


---  
 #  Seek : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[doubleinteger](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/doubleinteger.markdown)| |
> |origin|[StreamOrigin](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#streamorigin)| |
> ``` lang=cpp, name=Zilch
> function Seek(position : DoubleInteger, origin : StreamOrigin) : Boolean
> ``` 


---  
 #  Write : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |data|Array[[byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)]| |
> ``` lang=cpp, name=Zilch
> function Write(data : Array[Byte]) : Integer
> ``` 


---  
 #  Write : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |data|Array[[byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)]| |
> |byteStart|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |byteCount|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Write(data : Array[Byte], byteStart : Integer, byteCount : Integer) : Integer
> ``` 


---  
 #  WriteByte : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)| |
> ``` lang=cpp, name=Zilch
> function WriteByte(p0 : Byte) : Integer
> ``` 


---  
 #  WriteText : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |text|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function WriteText(text : String) : Integer
> ``` 


---  
 #  WriteText : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |text|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |sourceStreamEncoding|[iencoding](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/iencoding.markdown)| |
> ``` lang=cpp, name=Zilch
> function WriteText(text : String, sourceStreamEncoding : IEncoding) : Integer
> ``` 


---  
 

 