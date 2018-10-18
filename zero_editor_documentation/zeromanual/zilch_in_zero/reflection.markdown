Reflection describes an objects ability to "reflect" on itself, generally this means to understand it's type and relationships to other types. Although Zilch does not boast a robust reflection library it does have a basic typeid for by-value types and [property_delegates](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/property_delegates.markdown):

 # typeid
```lang=csharp
  var i = 0;
  var di = 0d;
  var real = 0.0;
  var double = 0.0d;
  var word = "";
  var refType = null;
  var boolTrue = true;
  var boolFalse = false;
  var prop = new Property[Real]();        
  
  Console.Write("integer, 0 is of type: ");
  Console.WriteLine(typeid(i).Name);               // integer, 0 is of type: Integer
  Console.Write("doubleinteger, 0d is of type: ");
  Console.WriteLine(typeid(di).Name);              // doubleinteger, 0d is of type: DoubleInteger
  Console.Write("real, 0.0 is of type: ");
  Console.WriteLine(typeid(real).Name);            // real, 0.0 is of type: Real
  Console.Write("doublereal, 0.0d is of type: ");
  Console.WriteLine(typeid(double).Name);          // doublereal, 0.0d is of type: DoubleReal
  Console.Write("string, \"\" is of type: ");
  Console.WriteLine(typeid(word).Name);            // string, "" is of type: String
  Console.Write("null, null is of type: ");
  Console.WriteLine(typeid(refType).Name);         // refTypeHandle, null is of type: Null
  Console.Write("boolean, true is of type: ");
  Console.WriteLine(typeid(boolTrue).Name);        // boolean, true is of type: Boolean
  Console.Write("boolean, false is of type: ");
  Console.WriteLine(typeid(boolFalse).Name);       // boolean, false is of type: Boolean   
  Console.Write("Real property delegate is of type: "); 
  Console.WriteLine(typeid(prop).Name);            // Real property delegate is of type: Property[Real]
```


```name=Console Output
  ---------------- Begin Game ---------------
  integer, 0 is of type: Integer
  doubleinteger, 0d is of type: DoubleInteger
  real, 0.0 is of type: Real
  doublereal, 0.0d is of type: DoubleReal
  string, "" is of type: String
  null, null is of type: Null
  boolean, true is of type: Boolean
  boolean, false is of type: Boolean
  Real property delegate is of type: Property[Real]
```
--------------------
 # String Interpolation

Those types that are [memory_management](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown) or [delegates](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/delegates.markdown) types can be inspected with [string](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/zilch_base_types/string.markdown) Interpolation:

```lang=csharp
class Utility
{
  constructor()
  {
  }
  [Static]
  function HelloWorld()
  {
    Console.WriteLine("Hello World");
  }
  
  function Add(a: Integer, b: Integer): Integer
  {
    return a+b;
  }
}

class Driver 
{
  function TypeidForRefAndDelegates()
  {
    var del = Utility.HelloWorld;
    var temp = new Utility();
    var del2 = temp.Add;
    var vectorRef = new Real3(0.0, 1.0, 2.0);

    Console.Write("delegate(), Utility.HelloWorld can be string interpolated to read: "); 
    Console.WriteLine("`del`");
    
    Console.Write("delegate(a:Integer, b:Integer):Integer, Utility.Add");
    Console.Write(" can be string interpolated to read: ");
    Console.WriteLine("`del2`");

    
    Console.Write("ref Real3, (0.0, 1.0, 2.0) is of type: ");
    Console.WriteLine("`vectorRef`");
  }
}
```


```name=Console Output
---------------- Begin Game ---------------
delegate(), Utility.HelloWorld can be string interpolated to read: Utility.HelloWorld()
delegate(a:Integer, b:Integer):Integer, Utility.Add can be string interpolated to read: 
Utility.Add(a : Integer, b : Integer) : Integer
ref Real3, (0.0, 1.0, 2.0) is of type: ref Real3
```
--------------

 # Console.DumpValue

Useful in understanding the current state of a Zilch object, Console.DumpValue prints out the names of the variables and their type, if a [class](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown), or their value if a basic, built-in data type.

```lang=csharp
class TopLevel
{
  var MyVariable: MidLevel = null;
  constructor()
  {
  }
}

class MidLevel
{
  var MyVariable: BottomLevel = BottomLevel(false);
  constructor()
  {
  }
}

struct BottomLevel
{
  var IsBottom: Boolean = true;
  var UpAxis: Real3 = Real3(0.0, 1.0, 0.0);
  constructor(param: Boolean)
  {
    this.IsBottom = param;
  }
}
    
class ReflectionDriver
{
  [Static]
  function Dumping()
  {
    var top = TopLevel();
    var mid = MidLevel();
    var bot = BottomLevel(true);
    
    Console.DumpValue(top);
    Console.DumpValue(mid, 8); // The second parameter indicates the depth of recursion cut-off
    Console.DumpValue(bot);
    
  }
}
```

```name=Console Output
---------------- Begin Game ---------------
TopLevel
  MyVariable: (null) MidLevel
MidLevel
  MyVariable: BottomLevel
    IsBottom: False
    UpAxis: (0, 1, 0)
      X: 0
      Y: 1
      Z: 0
BottomLevel
  IsBottom: True
  UpAxis: (0, 1, 0)
```

*Notice how the MidLevel dumps more information than the BottomLevel with comparable information, due to the second parameter.*

 # Related Materials
 ## Manual

- [property_delegates](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/property_delegates.markdown)
- [memory_management](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown)
- [delegates](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/delegates.markdown)
- [string](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/zilch_base_types/string.markdown)
- [classes](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
 

 