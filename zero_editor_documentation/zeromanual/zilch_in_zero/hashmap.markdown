A HashMap is a templated data structure that can map unique keys of type A to values of type B (where A and B can be the same type).

 # Declaration

NOTE: The types `HashMap` and `KeyValue` not currently appear in the [zilch_base_types](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types.markdown) list and does not currently show up in code completion suggestions (T552) during initial declaration.

HashMap declaration is similiar to the declaration of any templated type in Zilch. When a HashMap is created, by default, it has no elements.

```name=HashMap Declaration Example, lang=csharp
var namesToObjects = HashMap[String, Cog]();
var idToCost = HashMap[Integer, Real]();
var spawnerToEnemyType = HashMap[Cog, Archetype]();
var enemyType = HashMap[Archetype, Integer]();
```

HashMaps have a variety of uses. One may use them to keep track of objects at runtime by an alternate name, or to keep count of how many of each enemy archetype a spawner has created at runtime. Below are some simple example of HashMap functionality which map unique [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown) keys to non-unique [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown) values.

 ## Initialization
It is common for a HashMap to be populated at runtime, but it is also possible to define elements within an initializer list.

```name=Initializer List Example, lang=csharp
var hash = HashMap[Integer, String]()
{
  {1, "one"},
  {2, "two"},
  {3, "three"}
};
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20744110) 
{
  {2, two}
  {1, one}
  {3, three}
}
```

Notice that the order in which the elements are printed is not the order in which they were added to the HashMap. This is due to HashMaps having no inherent order, unlike [Arrays](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t.markdown). Instead of the pairs being printed in an indexed order they are printed in an arbitrary order based on the hash of the pair.

NOTE: The HashMap templated type is currently lacking templated print functionality similiar to [Arrays](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/arrays.markdown). The `PrintHashMap` function used in this page is implemented below:

```name=PrintHashMap, lang=csharp
function PrintHashMap(hash : HashMap[Integer, String])
{
  Console.WriteLine("`hash` \n{");
  foreach(var pair in hash.All)
  {
    Console.WriteLine("  {`pair.Key`, `pair.Value`}");
  }
  Console.WriteLine("}");
}
```

 # HashMap Access
HashMap elements can be accessed for reading or writing in a few different ways which have different primary use cases.

 ## The `[]` Operator
The `[]` (pronounced subscript) operator is the primary way to access any *value// within a HashMap. When a valid //key* is passed to the subscript operator the corresponding value is returned from the HashMap. The `[]` operator can also be used to assign new values to keys within the HashMap.

```name=[] Operator Example, lang=csharp
var hash = HashMap[Integer, String]()
{
  {1, "one"},
  {2, "two"}
};
hash[3] = "three";
Console.WriteLine(hash[1]);
Console.WriteLine(hash[2]);
Console.WriteLine(hash[3]);
```
```name=Console Output
one
two
three
```

IMPORTANT: If an invalid key is passed to the `[]` operator a runtime exception will be thrown: ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90723.png)

 ## Get Functions
Another way to access the `KeyValue` pairs of a HashMap is to use the `get` functions.

 ### HashMap.Get
`HashMap.Get` behaves the same as the `[]` operator, as it is the function actually called by the `[]` operator. However, being a function, `Get` can be referenced by a delegate.

```name=HashMap.Get Example, lang=csharp
var hash = HashMap[Integer, String]()
{
  {1, "one"},
  {2, "two"},
  {3, "three"}
};
Console.WriteLine(hash.Get(1));
Console.WriteLine(hash.Get(2));
Console.WriteLine(hash.Get(3));
```
```name=Console Output
one
two
three
```

 ### HashMap.GetOrDefault
`HashMap.GetOrDefault` behaves the same as [Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-get), but instead of throwing an exception when passed an invalid key it returns a *default// value that is the same type as the //values* of the HashMap.

```name=HashMap.GetOrDefault Example, lang=csharp
var hash = HashMap[Integer, String]()
{
  {1, "one"},
  {2, "two"},
  {3, "three"}
};
Console.WriteLine(hash.GetOrDefault(1, "default"));
Console.WriteLine(hash.GetOrDefault(2, "default"));
Console.WriteLine(hash.GetOrDefault(3, "default"));
Console.WriteLine(hash.GetOrDefault(4, "default"));
Console.WriteLine(hash.GetOrDefault(5));
```
```name=Console Output
one
two
three
default
(null) String
```

 ### HashMap.GetOrError
`GetOrError` has the same functionality as [Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-get), the only difference being that it is not called by the `[]` operator.

 # Adding to a HashMap
There are multiple ways to add `KeyValue` pairs to HashMaps. [Add](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-add), [Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-set), and the `[]` operator can all be used to add `KeyValue` pairs to the HashMap.

 ## HashMap.Add
`Add` takes a *key* and //value//, adding the pair to the HashMap. If the given key already exists then a runtime exception will be thrown.

```name=Add, lang=csharp
var hash = HashMap[Integer, String]();
hash.Add(1, "one");
hash.Add(2, "two");
hash.Add(3, "three");
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20744110) 
{
  {2, two}
  {1, one}
  {3, three}
}
```

It should be noted that the `Add` function is called for each `KeyValue` pair when a HashMap is populated using an initializer list.

 ## HashMap.Set
`Set` is very similar to [Add](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-add). `Set` takes a *key// and //value//, adding the pair to the HashMap if the key does not exist. If the key does exist then the //value* paired with the given key will be replaced with the //given value//.

```name=Set, lang=csharp
var hash = HashMap[Integer, String]();
hash.Set(1, "one");
hash.Set(2, "two");
hash.Set(2, "three");
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20744110) 
{
  {2, three}
  {1, one}
}
```

 ### HashMap.SetOrOverwrite
The relationship of [Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-set) and `SetOrOverwrite` is simliar to that of [Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-get) and [GetOrError](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-getorerror) in that they have the same behavior. However, like [Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-get), [Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-set) is called by the `[]` operator during assignment.

```name=SetOrOverwrite, lang=csharp
var hash = HashMap[Integer, String]();
hash.SetOrOverwrite(1, "one");
hash.SetOrOverwrite(2, "two");
hash.SetOrOverwrite(2, "three");
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20744110) 
{
  {2, three}
  {1, one}
}
```

 ### HashMap.SetOrIgnore
`SetOrIgnore` behaves the same as [Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-set) except if the given *key* already exists the function returns leaving the HashMap unmodified.

```name=SetOrIgnore, lang=csharp
var hash = HashMap[Integer, String]();
hash.SetOrIgnore(1, "one");
hash.SetOrIgnore(2, "two");
hash.SetOrIgnore(2, "three");
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20744110) 
{
  {2, two}
  {1, one}
}
```

 ### HashMap.SetOrError
`SetOrError` follows a similiar behavior to [GetOrError](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/hashmap/.markdown#hashmap-getorerror). If the key passed to `SetOrError` already exists in the HashMap then an exception will be thrown.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90732.png)


 # HashMap Container Operations
 ## HashMap.Clear
The `Clear` function simply removes all `KeyValue` pairs from the HashMap.

```name=Clear Example, lang=csharp
var hash = HashMap[Integer, String]();
hash[1] = "one";
hash[2] = "two";
hash[3] = "three";
this.PrintHashMap(hash);
hash.Clear();
this.PrintHashMap(hash);
```
```name=Console Output
HashMap[Integer, String] (20712538) 
{
  {2, two}
  {1, one}
  {3, three}
}
HashMap[Integer, String] (20712538) 
{
}
```

 ## HashMap.Contains
`Contains` takes a parameter matching the *key* type of the HashMap and returns `true` if the given key exists in the HashMap.

```name=Contains Example, lang=csharp
var hash = HashMap[Integer, String]();
hash[1] = "one";
hash[2] = "two";
hash[3] = "three";
this.PrintHashMap(hash);
Console.WriteLine("This HashMap contains the key 2: `hash.Contains(2)`");
Console.WriteLine("This HashMap contains the key 4: `hash.Contains(4)`");
```
```name=Console Output
HashMap[Integer, String] (20713030) 
{
  {2, two}
  {1, one}
  {3, three}
}
This HashMap contains the key 2: true
This HashMap contains the key 4: false
```

 # HashMap Range Functions
There are a number of HashMap properties providing iterable ranges that are particularly useful for examining each pair in a HashMap.

 ## HashMap.All
Contains an iterable range of all `KeyValue` pairs in the HashMap.
```name=PrintHashMap, lang=csharp
function PrintHashMap(hash : HashMap[Integer, String])
{
  Console.WriteLine("`hash` \n{");
  foreach(var pair in hash.All)
  {
    Console.WriteLine("  {`pair.Key`, `pair.Value`}");
  }
  Console.WriteLine("}");
}
```
The `PrintHashMap` function is an excellent example of how one may use `All`.

 ## HashMap.Keys & HashMap.Values
`Keys` and `Values` return iterable ranges of containing the keys and values in the HashMap correspondingly.

 # HashMap.Count
`Count` returns the number of pairs in the HashMap.

 # Related Materials
 ## Manual
- [Arrays](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/arrays.markdown)
 ## Reference
- [Arrays](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t.markdown)
- [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)
- [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)
 ## Task
- T1317 
  
  
  
  
  
  
  

 