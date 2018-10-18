 `Component` `Engine`



(NOTE) Forms a link between two positions on two objects. ObjectLinks are used primarily by physics to represent joints, but can also be used by graphics, gameplay, etc... to represent some connection between two objects.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#objectlink-void)|[ LocalPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#localpointa-zero-engine)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
| |[ LocalPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#localpointb-zero-engine)| | |
| |[ ObjectA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#objecta-zero-engine-docu)| | |
| |[ ObjectAPath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#objectapath-zero-engine)| | |
| |[ ObjectB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#objectb-zero-engine-docu)| | |
| |[ ObjectBPath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#objectbpath-zero-engine)| | |
| |[ WorldPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectlink.markdown#worldpointb-zero-engine)| | |


 #  Properties


---  
 #  LocalPointA : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The Point on Object A in local space.
> ``` lang=cpp, name=Zilch
> var LocalPointA : Real3


---  
 #  LocalPointB : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The Point on Object B in local space.
> ``` lang=cpp, name=Zilch
> var LocalPointB : Real3


---  
 #  ObjectA : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> The first object that is being connected to. Set this to null to clear the link.
> ``` lang=cpp, name=Zilch
> var ObjectA : Cog


---  
 #  ObjectAPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cogpath.markdown)

> CogPath to object A.
> ``` lang=cpp, name=Zilch
> var ObjectAPath : CogPath


---  
 #  ObjectB : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> The second object that is being connected to. Set this to null to clear the link.
> ``` lang=cpp, name=Zilch
> var ObjectB : Cog


---  
 #  ObjectBPath : [cogpath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cogpath.markdown)

> CogPath to object B.
> ``` lang=cpp, name=Zilch
> var ObjectBPath : CogPath


---  
 #  WorldPointA : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The point on object A in world space.
> ``` lang=cpp, name=Zilch
> var WorldPointA : Real3


---  
 #  WorldPointB : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The point on object B in world space.
> ``` lang=cpp, name=Zilch
> var WorldPointB : Real3


---  
 #  Methods


---  
 #  ObjectLink : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ObjectLink()
> ``` 


---  
 

 