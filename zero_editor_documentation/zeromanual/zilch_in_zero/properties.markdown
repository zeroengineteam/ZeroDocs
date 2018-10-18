Get-Sets are syntactic sugar. They define two functions that look like variable usage.

```lang=csharp
class Example
{
  // This is a field.
  var SquareSideLength: Real = 2.0;
  
  // This is a property.
  var Perimeter : Real
  {
    get { return this.SquareSideLength * 4.0; }
    set { this.SquareSideLength = value * 0.25; }
  }
}

class Driver
{
  function Test()
  {
    // If we were to test it:
    var square = Example();
    // Nothing stops a user from setting the underlying value.
    square.SquareSideLength = 3.0;
    Console.WriteLine(square.Perimeter);          // 12.0
    Console.WriteLine(square.SquareSideLength);   // 3.0

    square.Perimeter = 1.0;                       // SquareSideLength = 0.25
    Console.WriteLine(square.Perimeter);          // 1.0
    Console.WriteLine(square.SquareSideLength);   // 0.25

    square.Perimeter = 8.0;                       // SquareSideLength = 2.0
  }
}
```
```name=Console Output
---------------- Begin Game ---------------
12
3
1
0.25
```

This get-set could easily be replaced by functions. The following is its equivalent:

```lang=csharp
class Example
{
  var SquareSideLength: Real = 2.0;
  
  function GetPerimeter(): Real
  {
    return this.SquareSideLength * 4.0;
  }
  
  function SetPerimeter(value: Real)
  {
    this.SquareSideLength = value * 0.25;
  }
}

class Driver
{
  function Test()
  {
    // If we were to test it we'd get the exact same results:
    var square = Example();
     // Nothing stops a user from setting the underlying value.
    square.SquareSideLength = 3.0;                
    Console.WriteLine(square.GetPerimeter());     // 12.0
    Console.WriteLine(square.SquareSideLength);   // 3.0

    square.SetPerimeter(1.0);                     // SquareSideLength = 0.25
    Console.WriteLine(square.GetPerimeter());     // 1.0
    Console.WriteLine(square.SquareSideLength);   // 0.25

    square.SetPerimeter(8.0);                     // SquareSideLength = 2.0     
  }
}
```
```name=Console Output
---------------- Begin Game ---------------
12
3
1
0.25
```
NOTE: Get-sets are not fields, and thus they have no storage of their own. If data state is needed you'll have to make another field on the class to which you may refer.  Although get-sets are not fields, fields can auto-generate the property interface using [property_delegates](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/property_delegates.markdown).

 # Parts of a Property's definition

```lang=csharp
// The type specified refers to BOTH the return type of the getter
// and the parameter type of the setter.
var Perimeter : Real // Despite ``var`` keyword, Properties have no storage.
{
  // get denotes the getter; it must return the type specified above.
  get { return this.SquareSideLength * 4.0; }  // Body of getter is wrapped in {}
  
  // set denotes the setter; it must accept the type specified above. 
  // value is a keyword that denotes the right hand side of the 
  // assignment operator as passed in from the user.
  set { this.SquareSideLength = value * 0.25; } // Body of setter is wrapped in {}
}
```
 # Related Materials
 ## Manual
- [property_delegates](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/property_delegates.markdown) 
  
  
  
  
  
  
  

 