This lesson covers loops in Zilch scripting.

 #  Learning Objectives

- When and how to write loops
- [while](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) and [for](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) loops
- Looping keywords: [continue](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) and [break](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- Infinite loops
- Nested loops

 #  Level Setup
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `LoopExamples`
- In the `LoopExamples` ZilchScript
 - Replace the script's contents with the following:
```lang=csharp, name="LoopExamples"
class LoopExamples : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    
  }
}
```
- In the `Objects Window`
 - [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : LoopExamples button 

 #  Getting Started

Recall the `Square` function from the [ Functions Tutorial](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/functions.markdown). It takes a Real parameter, multiplies it by itself, and returns the result:

```lang=csharp, name="Square"
function Square(number : Real) : Real
{
  return number * number;
}
```

Thus, the returned result of `Square(x)` is equal to `x` squared. But what about `x` cubed? Here's another function:

```lang=csharp, name="Cube"
function Cube(number : Real) : Real
{
  return number * number * number;
}
```

The result of `Cube(x)` equals `x` cubed. What about `x` to the fourth power, or the fifth, or the fifteenth? It would be impossible to write a function for every power to which a number could be raised. It is more practical to write a function that raises `x` to the `y` power, where `y` is another function parameter. This function multiplies a given `number` parameter by itself some variable number of times equal to a given `exponent` parameter. Let's begin writing an incomplete version of this function.

- In the `LoopExamples` ZilchScript resource
 - Add the following function to the `LoopExamples` class:

```lang=csharp, name="Incomplete Power Function, step 1"
function IncompletePower(number : Real, exponent : Integer) : Real
{
  var result = 1.0;
  var multiplications = 0;

  // math goes here

  return result;
}
```

This function has a `result` variable that will be returned at the end, but not before repeatedly multiplying it by `number`. It uses the `multiplications` variable to keep track of how many times it has performed that multiplication.

Now to fill in the math. Before each multiplication is done, if the number of multiplications is still less than the `exponent` passed into the function, then `result` gets multiplied by `number` again and again, checking each time.

- Add the following code to the `IncompletePower` function:

```lang=csharp, name="Incomplete Power Function, step 2"
function IncompletePower(number : Real, exponent : Integer) : Real
{
  var result = 1.0;
  var multiplications = 0;
  
  if (multiplications < exponent)
  {
    result *= number;
    ++multiplications;
  }
  if (multiplications < exponent)
  {
    result *= number;
    ++multiplications;
  }
  if (multiplications < exponent)
  {
    result *= number;
    ++multiplications;
  }
  if (multiplications < exponent)
  {
    result *= number;
    ++multiplications;
  }

  //
  // etc......
  //
  
  return result;
}
```

As its name implies, this function is incomplete, but it should work in some cases. Let's try it out, and compare it to Zilch's built-in exponentiation operator.

- Add the following code to the `Initialize` function:

```lang=csharp, name="IncompletePower Test"
function Initialize(init : CogInitializer)
{
  Console.WriteLine("IncompletePower: `this.IncompletePower(2.0, 2)`, x ^ y: `2.0 ^ 2`");
  Console.WriteLine("IncompletePower: `this.IncompletePower(2.0, 3)`, x ^ y: `2.0 ^ 3`");
  Console.WriteLine("IncompletePower: `this.IncompletePower(2.0, 4)`, x ^ y: `2.0 ^ 4`");
  Console.WriteLine("IncompletePower: `this.IncompletePower(2.0, 5)`, x ^ y: `2.0 ^ 5`");
  Console.WriteLine("IncompletePower: `this.IncompletePower(2.0, 6)`, x ^ y: `2.0 ^ 6`");
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
IncompletePower: 4, x ^ y: 4
IncompletePower: 8, x ^ y: 8
IncompletePower: 16, x ^ y: 16
IncompletePower: 16, x ^ y: 32
IncompletePower: 16, x ^ y: 64
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

The function works as intended if the desired power is small enough, but it will always return the same result for `exponent` values of 4 and above. To accommodate for larger powers, the `if`  block could be copied and pasted in additional times. That's a bad idea, though: the function would have to grow to a preposterous length for it to work with large powers. What this problem really needs is a loop.

 #  What is a Loop?

A **loop** is a block of code that runs multiple times. Normally, when a program runs, the computer executes each line of code in the program exactly once, in order. Code written in a loop, however, runs repeatedly, in some cases with slight variations from one iteration to the next.

There are several reasons to use loops. First of all, they serve the central tenet in programming that one should avoid writing the same code multiple times whenever possible. Second, changing a single loop is easier than making the same change to several repeated blocks of code. Third, loops are more visually compact and usually result in smaller file sizes. Finally, there are some problems that are nearly impossible to solve without loops.

Zilch recognizes several different kinds of loops; this lesson will cover two of the most common kinds.

 #  While Loops



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89904.png) *Figure 1: the anatomy of a `while` loop*


A **while loop** includes a *loop condition* and a //loop body//. The loop condition is a Boolean expression (that is, an expression that evaluates to a Boolean, regardless of the types it contains), and the loop body is zero or more statements.

When a `while` loop is executed...


#  The **loop condition** is evaluated.

 - If it equals `true`...

#  The **loop body** is run.

# Then the **loop condition** is checked again.
 - If it still equals `true`, the loop body runs again, and so on.

As long as the condition remains `true`, the body is repeatedly run.

Take another look at the `IncompletePower` function. Note that the *if* block is perfectly duplicated again and again, each time incrementing a variable and then checking that variable to determine whether it should run its contents. This is exactly what a `while` loop does, so rewriting this function to use a `while` loop should be very easy.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="WhileLoopPower Function"
function WhileLoopPower(number : Real, exponent : Integer) : Real
{
  var result = 1.0;
  var multiplications = 0;
  
  while (multiplications < exponent)
  {
    result *= number;
    ++multiplications;
  }
  
  return result;
}
```

Let's test this new version of the function.

- Replace the contents of the `Initialize` function with the following code:
```lang=csharp, name="WhileLoopPower Test"
function Initialize(init : CogInitializer)
{
  Console.WriteLine("WhileLoopPower: `this.WhileLoopPower(5.0, 6)`, x ^ y: `5.0 ^ 6`");
  Console.WriteLine("WhileLoopPower: `this.WhileLoopPower(Math.Pi, 7)`, x ^ y: `Math.Pi ^ 7`");
  Console.WriteLine("WhileLoopPower: `this.WhileLoopPower(0.1, 16)`, x ^ y: `0.1 ^ 16`");
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
WhileLoopPower: 15625, x ^ y: 15625
WhileLoopPower: 3020.29, x ^ y: 3020.29
WhileLoopPower: 1e-16, x ^ y: 1e-16
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

The results match. Of course, `WhileLoopPower` still has some severe limitations when compared to Zilch's exponentiation operator, perhaps the largest of which being that its exponent values must be nonnegative Integers.

 #  Infinite Loops

Let's look again at the loop inside the `WhileLoopPower` function:

```lang=csharp, name="While Loop Reexamined"
while (multiplications < exponent)
{
  result *= number;
  ++multiplications;
}
```

This runs over and over again, as long as `multiplications` is less than `exponent`. `multiplications` does eventually reach `exponent`, because it gets incremented with the `++` operator every loop iteration. What would happen if that didn't occur?

- Update the `WhileLoopPower` function with the following change:

```lang=csharp, name="Infinite Loop", counterexample
function WhileLoopPower(number : Real, exponent : Integer) : Real
{
  var result = 1.0;
  var multiplications = 0;
  
  while (multiplications < exponent)
  {
    result *= number;
    //++multiplications;
  }
  
  return result;
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

The editor hangs for a few moments, and then an exception is thrown:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90198.png) //Figure 2: infinite loop timeout. The error message reads: //Exceeded the allowed execution time of 5 second(s). Use the `timeout` statement to increase allowed time


Since the `++multiplications` statement has been commented out, the `while` loop's loop condition will always be true. Such a loop is called an **infinite loop**, or an *unconditional* loop. This is generally undesireable behavior.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Infinite loops are dangerous if handled improperly. Zero has timeout functionality to catch infinite loops, but at best, they will still throw an error and halt the game. (Other software might not be so forgiving.) Be aware that a simple mistake could lead to an infinite loop!

Let's move on to another kind of loop.

 #  For Loops

A `while` loop is simple: if the loop condition is true, the loop body continues to run; when it becomes false, it stops. The loop condition is usually dependent on some variable that was introduced earlier, and the loop body typically contains code that will eventually cause the loop condition to become false, thus breaking the loop so that the flow of the program can continue.

There is another kind of more specialized loop that builds some of these common elements into its syntax: the `for` loop.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89906.png) *Figure 3: the anatomy of a `for` loop*


A **for loop** contains a *loop condition// and a //loop body// just like a `while` loop, but it also has an //initialization statement* and an //update statement//. When a `for` loop is run...

#  The **initialization statement** is executed once at the beginning.

 - The initialization statement is usually used to declare a variable, known as an //iteration index//, or just an //index//, that typically appears in the loop condition.

#  Then the **loop condition** is checked.

 - As in a `while` loop, if the loop condition equals `true`...

#  The **loop body** runs next.

# After the loop body runs, the **update statement** is executed.
 - The update statement is usually used to increment the index — typically taking it one step closer to making the loop condition become `false`.

#  Then the **loop condition** is checked again.

 - If it still equals `true`, the loop body executes again, and so on.

As long as the condition remains `true`, the body is repeatedly run, and the update statement is executed at the end of each iteration.

Let's write a new version of `WhileLoopPower` that uses a `for` loop instead of a `while` loop.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="ForLoopPower Function"
function ForLoopPower(number : Real, exponent : Integer) : Real
{
  var result = 1.0;
  
  for (var multiplications = 0; multiplications < exponent; ++multiplications)
  {
    result *= number;
  }
  
  return result;
}
```

Compared to the `while` loop from before:
- the loop condition remains unchanged
- the loop body remains unchanged, except...
- the `++multiplications` expression has moved to the update statement
- the declaration of the `multiplications` variable has moved to the initialization statement

Let's test the new function with the same arguments that were supplied to the old one.

- Update the `Initialize` function with the following changes:

```lang=csharp, name="ForLoopPower Test"
function Initialize(init : CogInitializer)
{
  Console.WriteLine("ForLoopPower: `this.ForLoopPower(5.0, 6)`, x ^ y: `5.0 ^ 6`");
  Console.WriteLine("ForLoopPower: `this.ForLoopPower(Math.Pi, 7)`, x ^ y: `Math.Pi ^ 7`");
  Console.WriteLine("ForLoopPower: `this.ForLoopPower(0.1, 16)`, x ^ y: `0.1 ^ 16`");
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
ForLoopPower: 15625, x ^ y: 15625
ForLoopPower: 3020.29, x ^ y: 3020.29
ForLoopPower: 1e-16, x ^ y: 1e-16
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

It's still the same as before. In general, **any `for` loop can be rewritten as a `while` loop, and vice versa**.

So, what happens if a loop is written inside another loop?

 #  Nested Loops

Let's write a function that draws boxes in the console.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="DrawBoxes Function"
function DrawBoxes(count : Integer)
{
  for (var i = 0; i < count; ++i)
  {
    Console.Write("[]");
  }

  Console.WriteLine();
}
```

`DrawBoxes` takes an Integer argument and draws that many boxes to the console.

A few remarks:
- the index of a `for` loop is conventionally named `i`
- the body of the loop calls `Console.Write` instead of `Console.WriteLine` so that more than one box can be drawn on the same line
- after the end of the loop, `Console.WriteLine` is called with no arguments, just to write a newline to the console. This way, the next time something is printed, it will appear on the next line down instead of on the same line as the boxes

Let's try it out.

- Replace the contents of the `Initialize` function with the following code:

```lang=csharp, name="DrawBoxes Test"
function Initialize(init : CogInitializer)
{
  this.DrawBoxes(10);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
[][][][][][][][][][]
```

Everything seems to be in order, but regardless of what number is passed into the function, all the boxes will always be drawn on the same line. In order to create multiple rows of boxes, the `DrawBoxes` function should employ another looping concept, called a nested loop.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

The `DrawBoxes` function, as it exists right now, already does a perfectly good job of drawing a single row of boxes. The only modification it needs is to make its contents run several times. And what is a good way to make code run several times? Of course, it's a loop. A **nested loop** is a loop written inside the body of another loop. Nested loops are often used in multi-dimensional tasks, such as drawing a 2D grid of boxes.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="DrawBoxesInGrid Function"
function DrawBoxesInGrid(columns : Integer, rows : Integer)
{
  var totalBoxesDrawn = 0;
  
  for (var i = 0; i < rows; ++i)
  {
    for (var j = 0; j < columns; ++j)
    {
      Console.Write("[]");
      ++totalBoxesDrawn;
    }
    
    Console.WriteLine();
  }
  
  Console.WriteLine("Total boxes drawn: `totalBoxesDrawn`");
}
```

A few remarks:
- in a nested loop, it is customary to use `i` for the index of the outer loop and `j` for the index of the inner loop
- the entire contents of the function as written before have been placed inside the outer loop
- also, for reference purposes, the function now keeps track of how many boxes have been drawn, and prints the number at the end

The key thing to understand here is that in each iteration of the outer loop, the inner loop runs anew in its entirety. When a nested `for` loop runs...


#  The **outer initialization statement** is executed once at the beginning of the outer loop.

# Then the **outer loop condition** is checked. If it equals `true`...

#  The **outer loop body** runs. The outer loop body contains the inner loop.

 # The **inner initialization statement** is executed once at the beginning of the inner loop.
 # Then the **inner loop condition** is checked. If it equals `true`...
 # The **inner loop body** runs.
 # Then the **inner update statement** is executed.
 # Then the **inner loop condition** is checked again, and if it equals `true`, the inner loop continues to run until it is complete.
  - When the inner loop completes, every variable declared within its scope is cleaned up, //including anything declared in its initialization statement//.

#  Then the **outer update statement** is executed.

# Then the **outer loop condition** is checked again, and if it equals `true`...

#  The **outer loop body** runs. The outer loop body contains the inner loop.

 # The **inner initialization statement** is executed again, because it is now the beginning of the inner loop again.
  - Anything that was initialized here before fell out of scope and was cleaned up at the end of the inner loop, so it can be declared anew with the same identifier name.
 # Then the **inner loop condition** is checked again, and the inner loop continues to run until it is complete.

#  Then the **outer update statement** is executed again.

# Then the **outer loop condition** is checked again, and if it equals `true`, the nested loop continues to run in this manner until the outer loop is complete.

Let's try out the function.

- Update the `Initialize` function with the following changes:

```lang=csharp, name="DrawBoxesInGrid Test"
function Initialize(init : CogInitializer)
{
  this.DrawBoxesInGrid(8, 4);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
[][][][][][][][]
[][][][][][][][]
[][][][][][][][]
[][][][][][][][]
Total boxes drawn: 32
```

Four perfect rows of eight boxes each!

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Loops can be nested arbitrarily deep: a 3D array of boxes, for example, would call for a loop within a loop within a loop, and if each box is also a container that can hold objects, still another loop could be used to populate each one.

 #  Loop Keywords

There are two keywords that can be used to further control the execution flow through a loop: **continue** and **break**. Each of these statements is used to move the program flow to a different point, but it is important to remember that each of them functions **only on the most nested loop scope** in which it appears.

 ##  Continue



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89994.png) *Figure 4: program flow controlled by `continue`*


The `continue` statement jumps the program flow forward to the very end of the body of the current loop iteration (in a `for` loop, just before the update statement is executed). Nothing between the `continue` statement and the end of the loop body is executed. Effectively, it skips ahead to the next iteration.

Let's return to the `DrawBoxes` function. What if we want it to skip a given spot in the grid, not draw a box there, but leave it blank, and keep going afterward? This is a good task for the `continue` keyword.

First off, the function needs to take two new Integer parameters, specifying the column-row coordinates of the box to skip, designated as `skipX` and `skipY`. Then, when the `i` value (counting the rows) matches the given `skipY` value *and* `j` (counting the columns) matches `skipX`, instead of drawing a box, the function should print a blank space and then `continue`.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="Continue Example"
function DrawBoxesWithGap(columns : Integer, rows : Integer, skipX : Integer, skipY : Integer)
{
  var totalBoxesDrawn = 0;
  
  for (var i = 0; i < rows; ++i)
  {
    for (var j = 0; j < columns; ++j)
    {
      if (i == skipY && j == skipX)
      {
        Console.Write("  ");
        continue;
      }
      
      Console.Write("[]");
      ++totalBoxesDrawn;
    }
    
    Console.WriteLine();
  }
  
  Console.WriteLine("Total boxes drawn: `totalBoxesDrawn`");
}
```

Now to test it out.

- Update the `Initialize` function with the following changes:

```lang=csharp, name="Continue Test"
function Initialize(init : CogInitializer)
{
  this.DrawBoxesWithGap(8, 4, 6, 2);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
[][][][][][][][]
[][][][][][][][]
[][][][][][]  []
[][][][][][][][]
Total boxes drawn: 31
```

The specified box is skipped, and the printed total reflects this.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 ##  Break



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89999.png) *Figure 5: program flow controlled by `break`*


The `break` statement *breaks* the looping flow of the program, skipping any remaining loop iterations, as well as any code remaining in the current iteration. Effectively, it leaves the loop altogether.

In `DrawBoxes`, what if we want to specify a maximum number of boxes that should be drawn, regardless of the other given values? If, say, ten rows and ten columns are specified, but with a max of 40, then only forty boxes should be drawn, even though ten times ten is a hundred. A `break` statement is just right for this.

First of all, yet another new Integer parameter is needed for the `DrawBoxes` function, `max`, which specifies the maximum number of boxes to draw. Since the function already keeps track of the number that have been drawn so far, it only needs to check before drawing to see if it's hit the max. If it has, then a `break` statement should be executed.

- Add the following function to the `LoopExamples` class:

```lang=csharp, name="Break Example, step 1"
function DrawBoxesWithMax(columns : Integer, rows : Integer, max : Integer)
{
  var totalBoxesDrawn = 0;
  
  for (var i = 0; i < rows; ++i)
  {
    for (var j = 0; j < columns; ++j)
    {
      if (totalBoxesDrawn >= max)
        break;
      
      Console.Write("[]");
      ++totalBoxesDrawn;
    }
    
    Console.WriteLine();
  }
  
  Console.WriteLine("Total boxes drawn: `totalBoxesDrawn`");
}
```

Now to test the changes.

- Update the `Initialize` function with the following changes:

```lang=csharp, name="Break Test"
function Initialize(init : CogInitializer)
{
  this.DrawBoxesWithMax(10, 10, 40);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
[][][][][][][][][][]
[][][][][][][][][][]
[][][][][][][][][][]
[][][][][][][][][][]






Total boxes drawn: 40
```

Only forty boxes are drawn (and the specified box is still skipped). There's an awful lot of blank space, though, after the last box. This is because the `break` statement only causes the inner loop to end. The outer loop keeps running, writing another newline to the console with each iteration.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

To modify the function to make it break out of both loops, just add a Boolean variable that keeps track of whether the max has been reached. In the inner loop, if the function has drawn enough boxes, before breaking, set that variable to be `true`. In the outer loop, just after the inner loop is complete, check it. If it's true, `break` again.

- Update the `DrawBoxesWithMax` function with the following changes:

```lang=csharp, name="Break Example, step 2"
function DrawBoxesWithMax(columns : Integer, rows : Integer, max : Integer)
{
  var totalBoxesDrawn = 0;
  var maxReached = false;
  
  for (var i = 0; i < rows; ++i)
  {
    for (var j = 0; j < columns; ++j)
    {
      if (totalBoxesDrawn >= max)
      {
        maxReached = true;
        break;
      }
      
      Console.Write("[]");
      ++totalBoxesDrawn;
    }
    
    if (maxReached)
      break;
    
    Console.WriteLine();
  }
  
  Console.WriteLine("Total boxes drawn: `totalBoxesDrawn`");
}
```

Let's test out this final modification.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

```name="Console output"
[][][][][][][][][][]
[][][][][][][][][][]
[][][][][][][][][][]
[][][][][][][][][][]
Total boxes drawn: 40
```

Forty boxes were drawn, and the loop stops after they're all done.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 ###  Breaking an Infinite Loop

Rarely, it's actually desirable to create a loop that is intentionally unconditional, as long as it contains at least one code path to a `break` statement. This technique is used sparingly; it generally only occurs when the loop's exit conditions are too complex or numerous to fit comfortably in its definition.

 #  Related Materials
 ##  Manual
- [ Looping](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/looping.markdown)
- [ Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/launchernewproject.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [while](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- [keywords](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)

 ##  Tutorials
- [ Functions Tutorial](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/functions.markdown)

 ## Reference
 ### Zilch Base Types
- [ Math](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/math.markdown)

 ### Commands
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)
 

 