Flags are very similar to [enums](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/enums.markdown) except that they are ordered like a bit field (i.e. increasing in powers of two starting at 1 by default). Flags can be defined with the **flags** keyword:

```lang=csharp, name=Flags Type Defined
flags Pizza 
{ 
  Sauce, 
  Cheese, 
  Pepperoni, 
  Sausage, 
  Peppers, 
  Onion, 
  Mushroom, 
  Pineapple, 
  CanadianBacon, 
  Artichokes 
}
```

The names flags enumeration line up with Integral Powers of two, the default starting value is `1`:

```
Console.WriteLine("Pizza.Sauce         as Integer: `Pizza.Sauce         as Integer`");
Console.WriteLine("Pizza.Cheese        as Integer: `Pizza.Cheese        as Integer`");
Console.WriteLine("Pizza.Pepperoni     as Integer: `Pizza.Pepperoni     as Integer`");
Console.WriteLine("Pizza.Sausage       as Integer: `Pizza.Sausage       as Integer`");
Console.WriteLine("Pizza.Peppers       as Integer: `Pizza.Peppers       as Integer`");
Console.WriteLine("Pizza.Onion         as Integer: `Pizza.Onion         as Integer`");
Console.WriteLine("Pizza.Mushroom      as Integer: `Pizza.Mushroom      as Integer`");
Console.WriteLine("Pizza.Pineapple     as Integer: `Pizza.Pineapple     as Integer`");
Console.WriteLine("Pizza.CanadianBacon as Integer: `Pizza.CanadianBacon as Integer`");
Console.WriteLine("Pizza.Artichokes    as Integer: `Pizza.Artichokes    as Integer`");
```

```name=Console Output
Pizza.Sauce         as Integer: 1
Pizza.Cheese        as Integer: 2
Pizza.Pepperoni     as Integer: 4
Pizza.Sausage       as Integer: 8
Pizza.Peppers       as Integer: 16
Pizza.Onion         as Integer: 32
Pizza.Mushroom      as Integer: 64
Pizza.Pineapple     as Integer: 128
Pizza.CanadianBacon as Integer: 256
Pizza.Artichokes    as Integer: 512
```

Flags are meant to work together; consider the following:

```lang=csharp, name=Adding Flags Together
var hawaiian : Pizza = Pizza.Sauce + Pizza.Cheese + Pizza.CanadianBacon + Pizza.Pineapple;
Console.WriteLine(hawaiian);
// Using bitwise and, '&', to determine if the hawaiian pizza has pepperoni on it
if ((hawaiian & Pizza.Pepperoni) != 0)
{
    Console.WriteLine("Hawaiian pizza has `Pizza.Pepperoni` on it.");
}
else 
{
    Console.WriteLine("Hawaiian pizza does not have `Pizza.Pepperoni` on it.");
}
```
```name=Console Output
---------------- Begin Game ---------------
Sauce | Cheese | Pineapple | CanadianBacon
Hawaiian pizza does not have Pepperoni on it.
```
*Notice how it prints all of the active flags*

Basically, flags are enums that assign the next value by multiplying the previous value by two. 
For instance, given:

```lang=csharp, name=Defining a Custom Value
flags Cookie
{
  ChocolateChips, 
  Raisins, 
  Oatmeal, 
  MacadamiaNuts = 3,
  Peanuts,
  Pecans, 
  Caramel,
  Ginger, 
  Cinnamon,
  Sugar = 3
}
```

The values are different:

```lang=csharp
Console.WriteLine("Cookie.ChocolateChips as Integer: `Cookie.ChocolateChips as Integer`");
Console.WriteLine("Cookie.Raisins        as Integer: `Cookie.Raisins        as Integer`");
Console.WriteLine("Cookie.Oatmeal        as Integer: `Cookie.Oatmeal        as Integer`");
Console.WriteLine("Cookie.MacadamiaNuts  as Integer: `Cookie.MacadamiaNuts  as Integer`");
Console.WriteLine("Cookie.Peanuts        as Integer: `Cookie.Peanuts        as Integer`");
Console.WriteLine("Cookie.Pecans         as Integer: `Cookie.Pecans         as Integer`");
Console.WriteLine("Cookie.Caramel        as Integer: `Cookie.Caramel        as Integer`");
Console.WriteLine("Cookie.Ginger         as Integer: `Cookie.Ginger         as Integer`");
Console.WriteLine("Cookie.Cinnamon       as Integer: `Cookie.Cinnamon       as Integer`");
Console.WriteLine("Cookie.Sugar          as Integer: `Cookie.Sugar          as Integer`");
```
```name=Console Output
Cookie.ChocolateChips as Integer: 1
Cookie.Raisins        as Integer: 2
Cookie.Oatmeal        as Integer: 4
Cookie.MacadamiaNuts  as Integer: 3
Cookie.Peanuts        as Integer: 6
Cookie.Pecans         as Integer: 12
Cookie.Caramel        as Integer: 24
Cookie.Ginger         as Integer: 48
Cookie.Cinnamon       as Integer: 96
Cookie.Sugar          as Integer: 3
```
*Notice how after MacadamiaNuts is set to 3, the increment is no longer on powers of 2*

The underlying structure is [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown); therefore, you could interpret Integers as a flags type:

```lang=csharp, name=Casting Integers to Flags
var random: Pizza = 583 as Pizza;
Console.WriteLine(random);
Console.WriteLine(7 as Cookie);
```
```name=Console Output
Sauce | Cheese | Pepperoni | Mushroom | Artichokes
ChocolateChips | Raisins | Oatmeal | MacadamiaNuts | Peanuts | Sugar
```
*Notice how flags print both enumerated values if the flags share the same underlying integer value.*

 # Flags Rules
 ## Identifier Capitalization
Identifiers for the flags type name and the enumerated values must be capitalized.

```lang=csharp, name=Invalid Value Capitalization
// This will not compile. 
flags Directions {up, down, left, right}
```
```name=Console Output
Enum declaration 'Directions' does not have a closing '}'. We found 'LowerIdentifier' but we
expected to find '}'.
```

```lang=csharp, name=Invalid Type Name Capitalization
// Neither will this.
flags directions {Up, Down, Left, Right}
```
```name=Console Output
Enum declaration is missing a name. Upper-camel case names are required here (use 'Directions'
instead of 'directions').
```

 ## Unique Identifiers
Identifiers for the enumerated values must be unique.

```lang=csharp, name=Duplicate Identifiers
// This will not compile.
flags Directions {Up, Down, Up, Down}
```
```name=Console Output
A value of the same name 'Up' has already been declared in the enum 'Directions'. Names must 
only be used once.
```

 ## Definition Scope
Flags cannot be defined inside classes, structs, or other enums.

```lang=csharp, name=Incorrectly Defined Inside a Class
// Classes cannot contain flags.
class FlagsWrapper
{
  // This won't compile.
  flags Directions {Up, Down, Left, Right};
}
```
```name=Console Output
Class declaration 'FlagsWrapper' does not have a closing '}'. We found 'flags' but we expected to find '}'.
```

 ## Representation
If there is no enumerated value the enum is represented as an Integer:
```lang=csharp, name=Integer That Does Not Map to Enum
Console.WriteLine((64) as Cookie);
```
```name=Console Output
64
```

 # Flags and Integers
As in other languages, Integers make up the backbone of how flags work, and thus they work together in many situations.

 ## Casting
Because of this, Zilch will implicitly cast from a flag to an Integer when necessary:

```lang=csharp, name=Implict Integer Cast
class FlagsExample
{
  [Static]
  // This function accepts an flags type.
  function AcceptsFlags(param: Pizza)
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

We can test the calls to these functions to see the interplay of casting:

```lang=csharp
var paramInt = 128;
var paramFlags = Pizza.Pineapple;

// This works, as you'd expect
Console.Write(paramFlags);
FlagsExample.AcceptsFlags(paramFlags);

// But if you want to accept an Integer in an enum's place you MUST cast. 
Console.Write(paramInt);
*FlagsExample.AcceptsFlags(paramInt); * Doesn't compile
FlagsExample.AcceptsFlags(paramInt as Pizza);
```
```name=Console Output
Pineapple turned into Pineapple!
128 turned into Pineapple!
```

```lang=csharp, name=Invalid Implicit Cast
// Attempting to pass an Integer without casting to an enum 
// will cause a compiler error
Console.Write(paramInt);
FlagsExample.AcceptsFlags(paramInt);
```
```name=Console Output
The function 'AcceptsFlags' exists, but could not be resolved since the 
types of the arguments used did not match. The arguments you gave were: 

  AcceptsFlags(Integer)

The possible choices were: 

  AcceptsFlags(param : Pizza)
```

```lang=csharp
// This also works as you'd expect. 
Console.Write(paramInt);
FlagsExample.AcceptsInt(paramInt);

// The flags type parameter is implicitly casted to an Integer and is then passed to the function. 
Console.Write(paramFlags);
FlagsExample.AcceptsInt(paramFlags);
```
```name=Console Output
128 turned into 128!
Pineapple turned into 128!
```

 ## Flag-Integer Operations

Flags can perform all operations as if they were Integers. For instance, you can perform all of the normal math operations as implicit conversion will happen as necessary from the enum type to Integer:

```lang=csharp, name=Flags Using Integer Operations
// Here you can see use of the +, -, *, /, (), ^ and % Integer operators.
var pizza = (Pizza.Sauce + Pizza.Cheese) ^ Pizza.Sausage % 
           Pizza.Mushroom - Pizza.Artichokes * Pizza.Peppers;
           
// When the math evaluates to an unaliased number, the variable, although still of the enum type, 
// prints out its integer value.
Console.WriteLine(pizza); 
Console.WriteLine(typeid(pizza).Name);
```

```name=Console Output
Sauce | Onion (-8159)
Pizza
```
You can see the typeid is not an Integer but Pizza. An Integer value was printed because there were flags with no alias in that maps all aspects of `-8159`. Because the type is still of the flags, you could pass it to our `FlagsExample.AcceptsFlags` function without issue. When an operation includes both a flags and an Integer the result is always promoted to the flags type. If you want an Integer either 
 - Declare the variable you are storing the result in as an Integer: `var result : Integer`
 - Cast it: `result as Integer`

 ## Caveat

Although flags cast to Integers, they **will not** cast to Integers to perform cross-flags operations.

```lang=csharp, name=Invalid Cross-Flags Operation
// This won't compile.
Console.WriteLine(Pizza.Pineapple + Cookie.Sugar);
```
```name=Console Output
The binary '+' operator 'Positive / Add' is not valid with 'Pizza' and 'Cookie'.
```

 # Related Materials
 # Manual
- [enums](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/enums.markdown)

 ## Code Reference
- [flags_reference](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/flags_reference.markdown)
- [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown) 

 