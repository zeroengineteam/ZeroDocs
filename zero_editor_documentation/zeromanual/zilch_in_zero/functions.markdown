A function is a named block of code (with its own [scope](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown#scope) that performs a task. Ideally, one function should perform just one task. A function may return a value of a specific [type](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown) based on the operation performed in the function or it may return nothing at all. Functions can also take in values of a specific type, which are called parameters, that are used and/or changed by the operation of the function.

Functions are declared using the **function** keyword:
```lang=csharp, name=Function Declaration
// Note:
// -function keyword is used
// -function name is capitalized
// -function name is followed by ()
// -when present parameters go in between ()
//  -parameter names must start with a lowercase character
//  -parameters must have their type specified
// -when a return type is present a colon ':' follows the ')' & the returned type follows the ':'
function MyFunctionName(param1: MyParamType1, param2: MyParamType2) : MyReturnType
{// Scope of the function in wrapped in {}
  // function operations within this scope.
  
  // return keyword used to pass back return value specified.
  return MyReturnType(param1 + param2);
}
```

 # Function Rules

There are a number of important rules that functions in Zilch must follow. If these rules are not followed, an error will be thrown, as can be seen in the examples below. 

 ## No Global Functions
Zilch **does not support** global functions. They must be contained within the scope of either a [class](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown) or [struct](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/structs.markdown). Thus, the above would actually be encased like this:

```lang=csharp, name=Function Defined Within a Class
class MyClassName
{
    function MyFunctionName(param1: MyParamType1, param2: MyParamType2) : MyReturnType
    {
        // Perform function operations here.
        return MyReturnType(param1 + param2);
    }
}
```

or this:
```lang=csharp, name=Function Defined Within a Struct
struct MyStructName
{
  function MyFunctionName(param1: MyParamType1, param2: MyParamType2) : MyReturnType
  {
    // Perform function operations here.
    return MyReturnType(param1 + param2);
  }
}
```
Otherwise you may see an error like this

```name=Console Window
Parsing could not be completed (we ran into something we didn't understand). The token we hit was 'function' with token type 'Function'.
```

 # The Static Keyword
Static functions can be implemented using the `[Static]` attribute. Operations performed by functions which are static should be independent of independent of any particular data of the class. This is important as static functions can also be called with out access to an instance of the class by referencing the function through the non-instantied type:

```lang=csharp, name=Static Function
class MyClass
{
  [Static] // Marking it static allows you to reference the function without creating an instance.
  function ClassName():String
  {
    return "MyClass";
  }
}
```
If we were to test it:
```
Console.WriteLine(MyClass.ClassName());
```
the result would be

```name=ConsoleWindow
MyClass
```
NOTE: Unlike other languages static functions **cannot** be called from an instance, **only** from the class name.

 # Function Naming

The first letter of a function name MUST be capitalized. While the rest of the name may remain un-capitalized, function names are traditionally written using [upper camel case](https://en.wikipedia.org/wiki/Camel_case) (e.g. `MyFunctionName` instead of `Myfunctionname`).

```lang=csharp, name=Incorrect Function Name
// Lowercase function name will cause a compiler error.
function myFunctionName() // This won't work..
{
  // Perform function operations here.
}
```

```name=Console Window
Function declaration is missing a name. Upper-camel case names are required here (use 'MyFunctionName' instead of 'myFunctionName').
```

 # Parameter and Variable Naming

Parameters and locally-scoped (to the function scope in this case) MUST start with a lowercase character. While the rest of the name may remain un-capitalized, parameter and local variables are traditionally written using lower camel case (e.g. `myParamName` instead of `myparamname`).

```lang=csharp, name=Incorrect Parameter Name
// Capitalized parameter identifiers will cause a compiler error.
function MyFunctionName(Param1: MyParamType) // This won't work.
{
  // Capitalized locally-scoped variables will also cause a compiler error.
  var Count: Integer = 10; // This won't work.
}
```

```name=Console Window
Function declaration 'MyFunctionName' has an invalid argument list. We found 'UpperIdentifier' but we expected to find ')'.
```
In this error, `UpperIdentifier` refers to the uppercase letter 'P' used in `Param1`. As this is unacceptable for a parameter name, the error states that it expects to find the closing parenthesis instead.

 # Return Types

Return types are appended to the function signature **after** the argument list separated by the `:` operator. When this is left off the return type is assumed to be Void. You can use the **return** keyword to return a value from the function; however, if the function signature has a Void return type, the return statement must be omitted.

```lang=csharp, name=Using return Without Specifying Return Type
// Leaving off the return value, assumes nothing is returned.
function MyFunctionName()
{
  // 8 will NOT be returned since the signature does not specify a 
  // return type (a compiler error will occur)
  return 8;
}
```

```name=Console Window
The return statement was not expected to return a '[ErrorType]' value, since the function does not declare it (no ':' at the end).
```

 ## Code Paths
Occasionally you will run into situations such as this:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66750.png)

If we look at the possible logical flows of the `FunctionThatReturns` it should be noted that either the `if` or `else` case will run, never both. However, if the `else` case were to run the function would never hit a `return` statement. Normally this would not be an issue, but in this case the `FunctionThatReturns` defines a return type and there is a way for the function to fail to do so. This is not ok as it essentially amounts to a dead end in code. This issue throws and exception until all *code paths* return a value of the correct type.

 # Related Materials
 ## Manual
- [attributes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [classes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
- [variables_and_data_types](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown)
- [classes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
- [structs](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/structs.markdown)
 

 