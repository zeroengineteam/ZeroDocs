[ResourceTable](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ResourceTable.markdown) is a resource that stores a collection of entries of a certain resource type for sampling during run-time. Sampling can be performed through three different interfaces: array, hashmap, and a [ weighted table](https://github.com/zeroengineteam/ZeroDocs.markdown#weightedtable-interface).




![ResourceTable1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47118.PNG)

ResourceTables store a homogeneous collection of entries. Pictured above is a table of [ Archetypes ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/archetypes.markdown). This can be switched to any other resource type or to strings.

ResourceTable entries are composed of three items:
 - **Name**: A name used for hashmap queries. This is sometimes used as a display name for the entry. Note: This name does not have to Value. 
 - **Value**: The actual resource/string of the entry.
 - **Weight**: The weight to use when randomly sampling the table. See the [ WeightedTable Interface](https://github.com/zeroengineteam/ZeroDocs.markdown#weightedtable-interface) section below for details.

All sampling functions for a ResourceTable return a [ResourceTableEntry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ResourceTableEntry.markdown). In addition to the above listed properties, the stored resource can also be looked up via the `Resource` property. Note: This must be casted to the correct resource type.

 #  Array Interface

ResourceTables can be accessed as an array at run-time. This is useful for a list of objects where order is important (e.g. generating UI). Given below is a simple example of using the array interface to spawn archetypes:

```lang=csharp 
  // Spawn each archtype one below another
  for(var i = 0; i < this.Table.Count; ++i)
  {
    var entry = this.Table[i];
    // The table can only return Resources. We have to cast to Archetype
    var archetype = entry.Resource as Archetype;
    // Arbitrary spawn position
    var pos = Real3(0, i * -10, 0);
    this.Space.CreateAtPosition(archetype, pos);
  }
```

 #  HashMap Interface

ResourceTable can also be used as a hashmap where the entry's name is the key.



![ResourceTable4](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47120.PNG)


 One such example is mapping button names to a resource. Pictured above is a table of Levels. A menu in a game could use the `Name` properties to populate the text on buttons. When a button is clicked, the easiest way to get the Level to load is to use the HashMap interface to look up the entry by name.

```lang=csharp
  function GetLevelByName(name : String) : Level
  {
    var entry = this.Table.GetOrNull(name);
    if(entry == null)
      throw new Exception("Level '`name`' didn't exist");
    return entry.Resource as Level;
  }
```

 #  WeightedTable Interface

The more interesting use of a ResourceTable is as a weighted probability table. A weighted probability table is used to sample items with a non-uniform distribution which can be thought of as rolling loaded dice.

The weighted table view should be used to more easily edit and visualize the weights. This can be done by pressing the "Swap View" button in the UI.



![ResourceTable2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47122.PNG)


 ##  Weight vs. Probability
Each entry in a table has a weight used to determine how likely it is to be randomly sampled. The weight is not to be confused with the actual probability of rolling an item though. An entry's probability is computed as its weight divided by the sum of all the weights in the table. In the above picture the "Can" has a weight of 0.66. The total weights in the table sum to 2.18. This means the "Can" has a probability of 0.66 / 2.18 = 0.30275 or approximately 31%.

 ##  Sampling the Table
ResourceTable can be sampled at run-time through the `Sample` function:

```lang=csharp
  function SpawnDropAt(pos : Real3)
  {
    // Sampling the weighted table requires two random numbers in the range of [0, 1)
    var entry = this.Table.Sample(this.RandomContext.Real(), this.RandomContext.Real());
    var archetype = entry.Resource as Archetype;
    this.Space.CreateAtPosition(archetype, pos);
  }
```
One of the most common uses of the weighted table is for a drop table. In the above example the table is randomly sampled to Spawn an Archetype at a given position. Note that the sample function requires two random numbers in the range of 0 to 1.

Additionally, ResourceTable exposes the `SampleIndex` function which returns the index into the table instead of the entry itself.

---

 #  Related Materials
 ##  Reference
 [ResourceTable](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ResourceTable.markdown)
 [ResourceTableEntry](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ResourceTableEntry.markdown)
 [Archetype](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Archetype.markdown)
 [RandomContext](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/RandomContext.markdown) 

 