(NOTE)**Advanced Users Only**: The use of the **new** and **local** [keywords](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) __**is not something most users need to be concerned with**__, as it is almost entirely #deprecated. Heap or stack allocation is almost always handled automatically by the engine based off whether the constructed type is a class or struct, however, **new** and **local** still remain in the language for explicit allocation practices. Users attemptting to use **new** or **local** keywords should be aware that they override the standard allocation functionality of Zilch, but reference counted garbage collection will still happen for objects explicitly constructed with **new** and **local**.

 # Local

When working with **by-value** types that have constructors, such as structs or more complex stack primitive data types, the keyword **local** may be used:

```lang=csharp
  var up : Real3 = local Real3(0.0, 1.0, 0.0);
  var stackStructInstance : CustomStruct = local CustomStruct();
```

The compiler will infer the use of local for by-value types:
```lang=csharp
  // This is also valid.
  var up : Real3 = Real3(0.0, 1.0, 0.0);
  var stackStructInstance : CustomStruct = CustomStruct();
```

 # New

When working with [classes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown), references, or other or anything located on the heap with a constructor, use the **new** keyword:

```lang=csharp
  var heapObject : CustomClass = new CustomClass();
  var heapStructInstance : CustomStruct = new CustomStruct();
```

Once again the compiler will infer the use of new for **by-ref** types:

```lang=csharp
    // This is also valid.
    var heapObject : CustomClass = CustomClass();
```

Since structs are by-value, in order to get a reference you **must** specify new.

```lang=csharp
    // This does not compile
    var heapStructInstance : CustomStruct = CustomStruct();
```

```name=Console Output
      The value being assigned to 'heapStructInstance' must be of type 'CustomStruct'. Its type is 'CustomStruct'.
```

 # Related Material
 ## Manual
- [keywords](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- [classes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
- [memory_management](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown) 
  
  
  
  
  
  
  

 