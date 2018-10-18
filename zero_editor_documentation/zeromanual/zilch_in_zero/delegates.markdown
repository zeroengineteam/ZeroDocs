Delegates allows you to hold a function pointer in a variable, and use them at a later time.

The following three classes will work together to demonstrate creating, defining, and calling delegates.

```
class DelegateHolder
{
  var Name : String = "Unnamed";
  var Greeting : delegate() = null;
  
  constructor(name: String)
  {
    this.Name = name;
  }
  
  function Introduce()
  {
    Console.WriteLine("Hi I'm `this.Name`");
  }
}

```

The `DelegateHolder` class contains a delegate member variable `Greeting` that is set in the [constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown#constructors-and-destruc) to the member function `Introduce()`.

```
class MyMathLib
{
  [Static]
  function Exponent(baseNum : Integer, exponent : Integer) : Integer
  {
    var num  = 1; // Start at baseNum ^ 0
    while(exponent > 0)
    {
      num = num * baseNum;
      --exponent;
    }
    return baseNum;
  }
}
```

The `MyMathLib` class contains just a single [static](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown#static) [function](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown) that returns the product of exponentiation. This function will be used to demonstrate how to use a delegate in the next and final class.

```
class DelegateDriver : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    this.DelegateSamples();
  }
  
  function DelegateSamples()
  {
    var gh = new DelegateHolder("gh");
    var ef = new DelegateHolder("ef");
    
    // Making a delegate:
    var getName : delegate() = gh.Greeting;  
    
    // Using a delegate:
    getName();                                // Hi I'm gh
    
    // Assigning a member function to a delegate:
    getName = ef.Greeting; 
    
    // Passing a delegate into a function:            
    DelegateDriver.DelegateCaller(getName);           // Hi I'm ef
    getName();                                // Hi I'm ef
    
    // Assigning a static function to a delegate:
    getName = DelegateDriver.DelegateTest;        
    getName();                                // 256
                                              
    DelegateDriver.DelegateCaller(getName);           // 256
                                              
    // Making a delegate:                                          
    var doMath : delegate(a: Integer, b: Integer): Integer = DelegateDriver.Add;
    
    Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 8
    Console.WriteLine(doMath(2,6));                       // 8
    
    doMath = DelegateDriver.Multiply;
    Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 15
    Console.WriteLine(doMath(2,6));                       // 12
    
    doMath = DelegateDriver.Subtract;
    Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 2
    Console.WriteLine(doMath(2,6));                       // -4
  }
  
  [Static]
  function Add(a: Integer, b: Integer): Integer
  {
    return a+b;
  }
  [Static]
  function Multiply(a: Integer, b: Integer): Integer
  {
    return a*b;
  }
  [Static]
  function Subtract(a: Integer, b: Integer): Integer
  {
    return a-b;
  }
  [Static]
  function BinaryIntOpsCaller(a: delegate(a: Integer, b: Integer):Integer):Integer
  {
    return a(5, 3);
  }
  [Static]
  function DelegateCaller(a: delegate())
  {
    a();
  }
  [Static]
  function DelegateTest()
  {
    var doMath : delegate(lhs : Integer, rhs : Integer): Integer = MyMathLib.Exponent;
    Console.WriteLine(doMath(2, 8));
  }
}

```


The `DelegateDriver` class covers a number of different ways to define and call a delegate. Lines 10 and 11 create two `DelegateHolder` objects, `gh` and `ef`, while line 14 creates a delegate variable that's set to the delegate variable found in object `gh`:

```name=Drive Lines 10 - 14, lang=csharp
var gh = new DelegateHolder("gh");
var ef = new DelegateHolder("ef");

var getName : delegate() = gh.Greeting;
```

 Line 17 demonstrates directly calling a delegate using a delegate variable, while line 20 reassigns that delegate to the delegate variable found in object `ef`:
```lang=csharp, name=Driver Lines 17 & 20
getName();    

getName = ef.Greeting;
```

Line 24 passes the delegate variable into a function, `DelegateCaller`, which is defined further down the script—that calls the delegate function of any delegate passed into it:
```lang=csharp, name=Driver Line 24
getName = DelegateDriver.DelegateTest;
```
Line 27 assigns a static function to the delegate variable, `DelegateTest`, which defines its own delegate function assigned the to `Exponent` function in `MyMathLib`:
```lang=csharp, name=Driver Line 27
getName = DelegateDriver.DelegateTest;
```
Line 30 then passes in the re-assigned variable back into the `DelegateCaller` function, showing that the `Exponent` function is still called:
```lang=csharp, name=Driver Line 30
DelegateDriver.DelegateCaller(getName);
```
Line 33 creates a new delegate variable assigning it to another static function, while lines 35 - 44 demonstrates passing a delegate (that is redefined a couple of times) into a function that expects a delegate as a parameter:
```lang=csharp, name=Driver Lines 33-44
var doMath : delegate(a: Integer, b: Integer): Integer = DelegateDriver.Add;
    
Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 8
Console.WriteLine(doMath(2,6));                       // 8

doMath = DelegateDriver.Multiply;
Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 15
Console.WriteLine(doMath(2,6));                       // 12

doMath = DelegateDriver.Subtract;
Console.WriteLine(DelegateDriver.BinaryIntOpsCaller(doMath)); // 2
Console.WriteLine(doMath(2,6));    
```
Attaching `DelegateDriver` to an object and running the project results in the following print statements in the `Console Window`:

```name=Console Output
---------------- Begin Game ---------------
Hi I'm gh
Hi I'm ef
Hi I'm ef
256
256
8
8
15
12
2
-4    
```

 # Named Parameters
IMPORTANT: At this time the names chosen for the parameters are part of the signature. In order for two function signatures to be the same the names chosen for the parameters must match:

```lang=csharp, name=MyMathLib
class MyMathLib
{
  [Static] // Note named parameters are lhs and rhs:
  function Exponent(lhs: Integer, rhs: Integer): Integer
  {
    return lhs^rhs;
  }
}
```

Consider these tests:

```lang=csharp, name=Invalid Delegate Parameter Names
class Driver
{
  function DelegateTest()
  {
    // Here the delegate has named parameters a and b:
    var doMath : delegate(a: Integer, b: Integer): Integer = MyMathLib.Exponent;// This won't compile.
  }
}
```

```name=Console Output
  The value being assigned to 'doMath' must be of type 'delegate (a : Integer, b : Integer) : Integer'. 
  Its type is 'delegate (lhs : Integer, rhs : Integer) : Integer'.
```

```lang=csharp, name=Excluded Parameter Names
class Driver
{
  function DelegateTest()
  {
    // When declaring a delegate you cannot exclude the parameter names:
    var doMath : delegate(Integer, Integer): Integer = MyMathLib.Exponent;// This won't compile.
  }
}
```

```name=Console Output
Function declaration 'delegate' has an invalid argument list. We found 'UpperIdentifier' but 
we expected to find ')'.
```

```lang=csharp, name=Correctly Named Parameters
class Driver
{
  function DelegateTest()
  {
    // Here, after making the parameter names match, does it work:
    var doMath : delegate(lhs: Integer, rhs: Integer): Integer = MyMathLib.Exponent;
    Console.WriteLine(doMath(2,8));
  }
}
```

```name=Console Output
---------------- Begin Game ---------------
256
```

 # Member Function Delegates
IMPORTANT: Delegates that point at member functions can create memory leaks if they make cycles. See [memory_management](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown) for more.

IMPORTANT: Delegates pointing to member functions will throw runtime errors if the instance it was bound with was destroyed:

```lang=csharp, name=Invalid Call to a Delegate from a Deleted Variable
  // Here are three Objects with the ability to hold delegates:
  var ab = new DelegateHolder("ab");
  var b = new DelegateHolder("b");
  
  ab.Greeting = b.Introduce;
  
  delete b;
  ab.Greeting(); // This throws a runtime error
```

```name=Console Output
Attempted to access a member of a null handle: Attempted to call a member function on a null object
```

 # Null Delegates

IMPORTANT: It is an illegal operation to call a null delegate, so be sure to initialize your delegates before calling!

```lang=csharp
// Here are three Objects with the ability to hold delegates:
var ab: delegate(a: Integer, b: Integer): Integer  = null;

ab(3, 6);// This throws a runtime error
```

```name=Console Output
Attempted to invoke a null delegate
```

 # Related Materials
 ## Manual
- [memory_management](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown)
- [classes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
- [attributes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown) 
  
  
  
  
  
  
  

 