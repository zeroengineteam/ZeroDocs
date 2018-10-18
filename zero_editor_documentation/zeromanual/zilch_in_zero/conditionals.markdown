Conditionals allow programs to ask questions and act or not act based of the results.

 # if
An `if` conditional evaluates a given statement that evaluates to a [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown) value and executes code in a block scope defined underneath if it evaluates to `true`.

```lang=csharp, name=if Conditional
var boolValue = true;
if(boolValue)
{
  Console.WriteLine("boolValue is true");
}

boolValue = false;
if(boolValue)
{
  Console.WriteLine("boolValue is still true");
}

Console.WriteLine("End of the example");
```
```name=Console window
boolValue is true
End of the example
```
`boolValue`, which initially stores `true`, is checked in the first `if` block.  Since `if` is given the value `true`, the following block scope is executed and the `Console.WriteLine` function is called.  It is good practice to have a program log it's activity for debugging certain values. The 'Console window' snippet above shows that `"boolValue is true"` and `"End of the example"` are printed.  Notice that the line `Console.WriteLine("boolValue is still true")` exists as well, but `"boolValue is still true"` is not printed.  This is because the second `if` is given the value `false`, instructing the program to not execute any code inside that conditional's block scope.

 ## Unnecessary Conditionals
Because `if` conditionals take boolean values, a literal value can also be used:

```lang=csharp, name=Tautology and Contradiction
if(true)
{
  Console.WriteLine("This is a tautology");
}

if(false)
{
  Console.WriteLine("This is a contradiction");
}
```
```name=Console window
This is a tautology
```
The first `if` conditional is known as a tautology, while the second is a contradiction.  A tautology is always true, and the code block will always execute.  A condtradiction is always false, and its code block will never be executed.  While these patterns have no practical purpose in a program, the ability to 'disable' a conditional can be a useful debugging tool, making minimal changes to the code:

```lang=csharp, name=Disabling an if conditional with a tautology
if(true /*myVar*/)
{
  Console.WriteLine("Is this line run?");
}
```
`myVar` is a variable defined somewhere, but the check to see if it has the value `true` has been commented out and replaced with the literal `true` in order to explicitlly test the code within the scope of the `if` block.

 # Else
An `if` conditional on its own has the power to decide between action and inaction, but often a decision is made between two different actions. The `else` conditional is used to execute code when the `if` condition fails.

```lang=csharp, name=else Conditional
if(false)
{
  Console.WriteLine("The if ran");
}
else
{
  Console.WriteLine("The else ran");
}
```
```name=Console window
The else ran
```
Under the code block of the first `if`, there is a code block paired with the [Keyword](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) `else`.  The value `false` if given to the `if` conditional, and so the `else` block is executed. In any `if`-`else` pair, exactly one of the two code blocks will run.

 ## Else If
While often for any given conditional there are only two outcomes, sometimes there are more. The `else if` keyword combinations allows the chaining of conditional statements.

```lang=csharp, name=else if Conditional
var valone = false;
var valtwo = false;

if(valone)
{
  Console.WriteLine("valone is true");
}
else if(valtwo)
{
  Console.WriteLine("valtwo is true");
}
else
{
  Console.WriteLine("neither valone or valtwo are true");
}
```
```name=Console window
neither valone or valtwo are true
```
In the example above `valone` is evaluated as `false` in the first `if` conditional. Since the first if fails the script continues to the `else if` and evaluates `valtwo` as `false` causing the script to continue to the `else` condition.

 # Condensed Conditionals

Conditionals don't always require the use of scope operators. If the code block underneath is only one line long, the `{` and `}` become unnecessary.

```lang=csharp, name=else if Conditional
var valone = false;
var valtwo = false;

if(valone)
  Console.WriteLine("valone is true");
else if(valtwo)
  Console.WriteLine("valtwo is true");
else
  Console.WriteLine("neither valone or valtwo are true");
```
```name=Console window
neither valone or valtwo are true
```
The above rewrite of the last code block illustrates how scoping brackets can be removed to make code more compact.

WARNING: Removing scope operators isn't always good practice, because they need to be added when a code block is more than one statement. Omitting scope operators can unintentionally change the scope of some code, and yet the script can still sucessfully compile.

 ##  Uncondensing else if
The `else if` conditional is actually an `else` conditional with an `if`-`else` pair afterwards. The fact that scope operators can be removed is the reason that `else if` is valid. Using this logic we can rewrite the last example with explcit scopes to make this clearer.


```lang=csharp, name=else if Conditional
var valone = false;
var valtwo = false;

if(valone)
{
  Console.WriteLine("valone is true");
}
else
{
  if(valtwo)
  {
    Console.WriteLine("valtwo is true");
  }
  else
  {
    Console.WriteLine("neither valone or valtwo are true");
  }
}
```
```name=Console window
neither valone or valtwo are true
```

`else if` may seem like a seperate keyword than `if` and `else` but it is actually just syntactical suger to make code easier to follow.

 # Boolean Operations
While conditionals a useful their real power comes when used in combination with [boolean_operators](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown). It is highly suggested you review this page.

 # Related Material
 ## Manual
- [keywords](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- [boolean_operators](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/boolean_operators.markdown)

 ## Code Reference
- [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)
 

 