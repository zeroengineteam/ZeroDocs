[ Conditionals](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/conditionals.markdown) allow a developer to make decisions in code based off of `true` & `false` values.

 #  Learning Objectives
 - Evaluating Expressions
 - Console Printing Expressions and their results
 - `if`, `else`, and `else if`

 #  Level Setup
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateTransform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createtransform)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
  - Create a ZilchScript resource using the Component template template and name it `ConditionalsLogic`
 - [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Transform object
 - In the `Properties Window`
   - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `icon=square-o, name = ConditionalsLogic`

 #  `if` Statements
An `if` statement evaluates an expression to a [Boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown) value of `true` or `false`. If the expression is true, code within the scope of the `if` statement will be executed, otherwise the application focus will skip over its scope.

- Update the `icon=square-o, name =ConditionalsLogic` script:
```lang=csharp, name=ConditionalsLogic Script
class ConditionalsLogic : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    if(true)
    {
      Console.WriteLine("This will print to console.");
    }
    
    if(false)
    {
      Console.WriteLine("This will not print to console.");
    }
  }
}
```
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name=Console Output
---------------- Begin Game ----------------
This will print to console.
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how the output displays only text within the `if(true)` conditional.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Boolean Operators
`if` statements are primarily used to determine whether an entire sequence results in `true` or `false`. By using [ Boolean Operators ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown) an entire sequence can be evaluated rather than a single variable.

The [ Equality Operator ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown#equality) `==` is used to determine if two values are the same. This is different than the [ Assignment Operator](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/operators_precedence_chart.markdown) `=` that is used to assign a new value to a variable.

NOTE: The Equality Operator is a type of comparison operator that returns a boolean operator. 

The [ Inequality Operator](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown#inequality) `!=` is used to determine if two values are not the same. As long as the two values are not exactly the same, the `if` statement will be evaluated as `true`.

The [ Negation Operator](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/operators_precedence_chart.markdown) `!` is used to reverse some values when possible. In the example below, the `!` operator is used to reverse the value of a boolean.

- Update the `icon=square-o, name =ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class ConditionalsLogic : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    var booleanTest = true;
    var comparison = false;
    
    // Check to see if the two have the same value.
    if(booleanTest == comparison)
    {
      Console.WriteLine("`true` and `false` are not the same thing.");
    }
    
    // If `false` is not the same as `true`
    if(booleanTest != comparison)
    {
      // Flips the `booleanTest` variable.
      booleanTest = !booleanTest;
    }
    
    // Check to see if the two have the same value.
    if(booleanTest == comparison)
    {
      Console.WriteLine("`false` and `false` are the same thing.");
    }
  }
}
```
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name=Console Output
---------------- Begin Game ----------------
false and false are the same thing.
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how `false` and `false` are the same, resulting in a `true` conditional.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 #  `else if` Statements

Where `if` statements determine if a situation is `true`, `else if` statements can determine if alternative situations are `true` as long as previous conditionals are `false`. `else` statements catch all remaining conditions.

- Update the `icon=square-o, name =ConditionalsLogic` script:
```lang=csharp, name=ConditionalsLogic Script
class ConditionalsLogic : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    var grade = 85;
    
    if(grade < 70)
      Console.WriteLine("Failing Grade");
    else if(grade < 80)
      Console.WriteLine("Grade: C");
    else if(grade < 90)
      Console.WriteLine("Grade: B");
    else
      Console.WriteLine("Grade: A");
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name=Console Output
---------------- Begin Game ----------------
Grade: B
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how the lines checking if `grade < 70` and `grade < 80` each ran first. They were skipped over since they evaluated to a `false` condition, but the `grade < 90` conditional was true. The remaining line containing an `else` conditional was not considered.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

`if` statements also can be used to evaluate the current state of a variable, such as time passed. This can be useful when evaluating variables.

- Update the `icon=square-o, name = ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class ConditionalsLogic : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    var timePassed = 0.01;
    
    // Has any time passed
    if(timePassed != 0 && timePassed < 10)
    {
      Console.WriteLine("Time Passed: `timePassed` seconds");
    }
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name = Console Output
---------------- Begin Game ----------------
Time Passed: 0.01 seconds
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice that the `if` statement is run and the `timePassed` variable was used.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Non-Bracketed Scopes

Once an `if` statement is found to be `true`, any code nested within is run. There are different ways to write these lines of code, based on what is easy to read and understand.

The most common way to follow an `if` statement is to use the brackets discussed above. This is best used when more than one line of code is needed to be run.

- Update the `icon=square-o, name = ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class NumberGenerator : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    if(true)
    {
      Console.WriteLine(1);
      Console.WriteLine(2);
      Console.WriteLine(3);
    }
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name = Console Output
---------------- Begin Game ----------------
1
2
3
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice that all three lines of code were run. All actions within brackets immediately following a `true` `if` statement will be performed.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

Alternatively, if only one line of code needs to be performed, it can be common practice to not use braces, as long as code it positioned properly.

- Update the `icon=square-o, name = ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class NumberGenerator : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    if(true)
      Console.WriteLine(1);
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name = Console Output
---------------- Begin Game ----------------
1
Level 'Level' was loaded.
Loaded level 0.00s
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

The line of code was run due being indented and following a `true` `if` statement. Indention matters as some code can be skipped over or even unintentionally run if not written correctly.

- Update the `icon=square-o, name = ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class NumberGenerator : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    if(false)
      Console.WriteLine(1);
    Console.WriteLine(2);
    Console.WriteLine(3);
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name = Console Output
---------------- Begin Game ----------------
2
3
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how `1` was never printed due to the `false` `if` statement, but `2` and `3` were.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

Only the first indented line following a `true` `if` statement is performed. This is why it is important to use brackets for more than one line, for readability purposes. The following code is exactly the same as the previous example except that the second and third lines printed to Console are indented as well.

- Update the `icon=square-o, name = ConditionalsLogic` script:

```lang=csharp, name=ConditionalsLogic Script
class NumberGenerator : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    if(false)
      Console.WriteLine(1);
      Console.WriteLine(2);
      Console.WriteLine(3);
  }
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name = Console Output
---------------- Begin Game ----------------
2
3
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how `2` and `3` were still printed to console, even though they match the indention of the line above it.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Nested `If Else` Statements

It is important to realize that `if` statements can be nested within one another. Further, `else` statements take advantage of scenarios where a statement returns false.

- Update the `icon=square-o, name =ConditionalsLogic` script:
```lang=csharp, name=ConditionalsLogic Script
class ConditionalsLogic: ZilchComponent
{
  // Ingredients Boolean
  var TwoSlicesOfBread : Boolean = true;
  var PeanutButter : Boolean = true;
  var Jelly : Boolean = false;
  var Bacon : Boolean = true;
  var Banana : Boolean = true;
  var Turkey : Boolean = false;
  
  function Initialize(init : CogInitializer)
  {
    // Can't have a sandwich without bread
    if(this.TwoSlicesOfBread)
    {
      // Continue if we have a source of protein
      if(this.PeanutButter || this.Turkey)
      {
        // If there is Peanut Butter...
        if(this.PeanutButter)
        {
          // Determine which Peanut Butter sandwich this is
          if(this.Jelly)
            Console.WriteLine("Peanut Butter and Jelly Sandwich");
          else
          {
            // Preface the sandwich type
            Console.Write("Elvis Sandwich");
            
            // If bacon exists, it's a true Elvis Sandwich
            if(this.Bacon)
              Console.Write(" with Bacon");
            
            Console.WriteLine();
          }
        }
        // Otherwise, we have Turkey
        else
          Console.WriteLine("Turkey Sandwich");
      }
      else // No protein
        // Blues Brothers Special
        Console.WriteLine("Wish Sandwich - Two slices of bread and you wish you had some meat");
    }
    // No Bread
    else
      Console.WriteLine("Not a sandwich");
  }
}
```
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

```name= Console Output
---------------- Begin Game ----------------
Elvis Sandwich with Bacon
Level 'Level' was loaded.
Loaded level 0.00s
```

Notice how the output tells the user what kind of sandwich they have based on the ingredients selected. The nested If Statements make it possible to follow through based on the Boolean variables

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 # Related Materials
 ## Manual
- [Boolean Operators](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown)
- [Conditionals](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/conditionals.markdown)
- [Variables and Data Types](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown)
- [Zilch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown)
- [Keywords](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- [Operators Precedence Chart](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/operators_precedence_chart.markdown)
- [ Boolean Operators ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown)
- [ Operator Precedence](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/operators_precedence_chart.markdown)
- [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 ## Reference
 ### Classes
- [ZilchScript](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/zilchscript.markdown)

 ### Zilch Base Types
- [Zilch Base Types](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types.markdown)

 ### Commands
- [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)
- [CreateTransform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createtransform) 
  
  
  
  
  
  
  

 