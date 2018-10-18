An enum, or enumerated type, is a set custom identifiers that are enumerated. An enumerated type may be defined with the **enum** keyword:

```lang=csharp, name=Enum Definition
enum ControllerButtons {Start, Select, Up=0, Down, Left, Right, A=0, B=1} // no semicolon
```

The names line up with incrementing [Integers](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown) where the default starting value is 0. The values can be manually set in which case the following values will increment off of that manually defined value. Note that to access these Integer values, the enum must be [casted](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/casting.markdown) to an Integer:
```lang=csharp, name=Casting Enums to Integers
Console.WriteLine("ControllerButtons.Start  = `ControllerButtons.Start  as Integer`  " );
Console.WriteLine("ControllerButtons.Select = `ControllerButtons.Select as Integer`  " );
Console.WriteLine("ControllerButtons.Up     = `ControllerButtons.Up     as Integer`  " );
Console.WriteLine("ControllerButtons.Down   = `ControllerButtons.Down   as Integer`  " );
Console.WriteLine("ControllerButtons.Left   = `ControllerButtons.Left   as Integer`  " );
Console.WriteLine("ControllerButtons.Right  = `ControllerButtons.Right  as Integer`  " );
Console.WriteLine("ControllerButtons.A      = `ControllerButtons.A      as Integer`  " );
Console.WriteLine("ControllerButtons.B      = `ControllerButtons.B      as Integer`  " );
```

```name=Console Window
---------------- Begin Game ---------------
ControllerButtons.Start  = 0  
ControllerButtons.Select = 1  
ControllerButtons.Up     = 0  
ControllerButtons.Down   = 1  
ControllerButtons.Left   = 2  
ControllerButtons.Right  = 3  
ControllerButtons.A      = 0  
ControllerButtons.B      = 1  
```

 # Enum Rules

There a number of rules that must be followed when defining enums. If these rules are not followed, an error will be thrown, as can be seen in the examples below.

 ## Type Name and Value Capitalization

Identifiers for the enum type name and the enumerated values must be capitalized.

```lang=csharp, name=Incorrect Value Identifiers
// This will not compile. 
enum Directions {up, down, left, right}
```

```name=Console Window
Enum declaration 'Directions' does not have a closing '}'. We found 'LowerIdentifier' but we expected to find '}'.
```

```lang=csharp, name=Incorrect Type Name Identifier
// This won't compile either.
enum directions {Up, Down, Left, Right}
```

```name=Console Window
Enum declaration is missing a name. Upper-camel case names are required here (use 'Directions'
instead of 'directions').    
```


 ## Unique Identifiers

Identifiers for the enumerated values must be unique.

```lang=csharp, name=Duplicate Identifiers
// This will not compile.
enum Directions {Up, Down, Up, Down}
```

```name=Console Window
A value of the same name 'Up' has already been declared in the enum 'Directions'. Names must 
only be used once.
```

 ## Definition Scope

Enums cannot be defined inside classes, structs, or other enums.

```lang=csharp, name=Incorrectly Defined Inside a Class
// Classes cannot contain enums.
class EnumWrapper
{
  // This won't compile.
  enum ControllerButtons {Start, Select, Up=0, Down, Left, Right, A=0, B=1}
}
```

```name=Console Window
Class declaration 'EnumWrapper' does not have a closing '}'. We found 'enum' but we expected to find '}'.
```

 # Enums and Integers

As in other languages, Integers make up the backbone of how enums work, and thus they work together in many situations.

 ## Casting

Because of this, Zilch will implicitly cast from an enum to an Integer when necessary:

Given this:

```lang=csharp, name=Controller Class and Buttons Enum
enum ControllerButtons {Start, Select, Up=0, Down, Left, Right, A=0, B=1}

class Controller
{
  [Static]
  // This function accepts an enum type.
  function AcceptsEnum(param: ControllerButtons)
  {
    Console.WriteLine(" turned into `param`!");
  }
  
  [Static]
  // This function accepts an integer type.
  function AcceptsInt(param: Integer)
  {
    Console.WriteLine(" turned into `param`!");
  }
}
```

We can test the calls to these [functions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown) to see the interplay of casting:

```lang=csharp, name=Implicit Enum Cast
var paramInt = 3;
var paramEnum = ControllerButtons.Right;

// This works, as you'd expect
Console.Write(paramEnum);
Controller.AcceptsEnum(paramEnum);

// But if you want to accept an Integer in an enum's place you MUST cast. 
Console.Write(paramInt);
Controller.AcceptsEnum(paramInt as ControllerButtons);
```

```name=Console Window
---------------- Begin Game ---------------
Right turned into Right!
3 turned into Right!    
```

```lang=csharp, name=Passing Integer to a Function That Expects Enum
// Attempting to pass an Integer without casting to an enum 
// will cause a compiler error
Console.Write(paramInt);
Controller.AcceptsEnum(paramInt);
```

```name=Console Window
The function 'AcceptsEnum' exists, but could not be resolved since the types of the arguments 
used did not match. The arguments you gave were: 

  AcceptsEnum(Integer)

The possible choices were: 

  AcceptsEnum(param : ControllerButtons)
```

```lang=csharp, name=Passing Enum to a Function That Expects Integer
// This also works as you'd expect. 
Console.Write(paramInt);
Controller.AcceptsInt(paramInt);

// The enum type parameter is implicitly casted to an Integer and is then passed to the function. 
Console.Write(paramEnum);
Controller.AcceptsInt(paramEnum);
```

```name=Console Window
---------------- Begin Game ---------------
3 turned into 3!
Right turned into 3!
```

 ## Enum-Integer Operations

Enums can perform all operations as if they were Integers. For instance, you can perform all of the normal Integer math operations as implicit conversion will happen as necessary:
```lang=csharp, name=Using Integer Operations on an Enum
// Here you can see use of the +, -, *, /, (), ^ and % Integer operators.
var math = (ControllerButtons.Start + ControllerButtons.Right) ^ ControllerButtons.Left % 
           ControllerButtons.Right - ControllerButtons.Right * ControllerButtons.Select;
           
// When the math evaluates to an unaliased number, the variable, although still of the enum type, 
// prints out its integer value.
Console.WriteLine(math); 
Console.WriteLine(typeid(math).Name);
```

```name=Console Window
---------------- Begin Game ---------------
-3
ControllerButtons
```
Notice that the typeid is not an Integer but `ControllerButtons`. An Integer value was printed because there was no alias in the enum that maps to `-3`.


Because the type is still that of the enum, it can be passed to the `Controller.AcceptsEnum()` function without issue.  

When an operation includes both an enum and an Integer the result is always promoted to the enum type. To get an Integer either 

- Declare the variable you are storing the result in as an Integer: `var result : Integer`
- Cast it: `result as Integer`

 ## Caveat

Although enums cast to Integers, they **will not** cast to Integers to perform cross-enum operations.

```lang=csharp, name=Invalid Cross-Enum Operation
// This won't compile.
Console.WriteLine(ControllerButtons.Down + Directions.Down);
```

```name=Console Window
The binary '+' operator 'Positive / Add' is not valid with 'ControllerButtons' and 'Directions'.
```

 # Related Materials
 ## Manual
- [casting](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/casting.markdown)
- [functions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown)

 ## Code Reference
- [enum_reference](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown)
- [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown) 
  
  
  
  
  
  
  

 