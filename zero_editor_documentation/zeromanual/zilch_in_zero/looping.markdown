Looping is a technique used to execute code an arbitrary number of times.

 # The Loop Keyword
The `loop` keyword defines the most basic type of looping structure in Zilch.  This is most useful when processing each element in a container, where the container size may not be known.

```lang=csharp, name=Loop
var i = 0;
var sum = 0;
loop
{
  sum += i;
  Console.WriteLine(sum);
  if (i >= 3)
    return;
  ++i;
}
```
```name=Console window
0
1
3
```
The values of `sum` printed are `0`, `1`, and `3` because `sum += 0`, `sum += 1`, and `sum += 2` are all executed in sequence with a call to `Console.WriteLine` after each.  Whatever code is in the block following `loop` will be repeatedly executed until the `loop` is escaped with `return`, [break](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/looping.markdown#navigating-loops), or [continue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/looping.markdown#continue).  `return` is a directive that leaves the [function](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown), and therefore can be used to exit a loop.

 # While and Do While
While the `loop` keyword is sufficient in executing code an arbitrary ammount of times, there are other types of loop blocks that make for cleaner code.

```lang=csharp, name=While
var i = 0;
var sum = 0;
while(i < 3)
{
  sum += i;
  Console.WriteLine(sum);
  ++i;
}
```
```name=Console window
0
1
3
```
The above snippet will sum together numbers in sequence like in the `Loop` code snippet, but this time using the `while` keyword.  `while` will run when `i` is `0`, `1`, and `2`, and the sequence of sums will be the same as in the `Loop` code snippet.

```lang=csharp, name=Do While 1
var i = 0;
var sum = 0;
do
{
  sum += i;
  Console.WriteLine(sum);
  ++i;
}
while(i < 3)
```
```name=Console window
0
1
3
```
The above snippet also produces the same result as the `While` code snippet, but with `do while` instead of `while`.  The `do while` structure is similar to a `while` loop, but with the looping condition is checked after the loop is run.  One should be mindful of the implications of `do while`, that whatever is in the code block following `do` will run at least once.  Still, the `do while` block is executed when `i` is `0`, `1`, and `2`.

```lang=csharp, name=Do While 2
var i = 100;
var sum = 0;
do
{
  sum += i;
  Console.WriteLine(sum);
  ++i;
}
while(i < 3)
```
```name=Console window
100
```
Notice how the above code snippet is a modification of `Do While 1`, showing how choosing the wrong type of loop can result in logical errors. The initial value of `i` is now `100`, and therefore the summation range is `[100,3]`.  In the field of mathematics, `[100,3]` is an empty interval, and the proper sum would be `0`.  Since a `do while` is used here, the result is instead `100`.  If the above example instead used a `while` loop, the code block would never execute and the result would be `0`.

 # For loop
A common use for looping is to iterate over a set, whether it's numbers or elements in a container.  The `for` loop provides an even shorter syntax than the `while` loop.

```lang=csharp, name=For
var myArray = Array[Integer]();
var sum = 0;
for (var j = 0; j < 3; ++j)
{
  myArray.Add(j);
}
Console.WriteLine(myArray);

for(var i = 0; i < 3; ++i)
{
  sum += myArray.Get(i);
  Console.WriteLine(sum);
}
```
```name=Console window
{0, 1, 2}
0
1
3
```
Notice how the above code snippet and the `While` code snippet loops produce the same result: `0`, `1`, and `3`.  First `i` is **initialized** to `0`.  Then in a loop, the `i < 3` **condition** is checked, `sum` is increased and printed, and `i` is incremented at the end of the **iteration**.  The `for` loop follows the format `for(<initialization>; <condition>; <iteration>)`.  In addition, the above code snippet uses an [array](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t.markdown). An array is a container with the *indexable* quality, which means the i-th element can be directly accessed.  This access is done by calling the function `myArray.Get`.

 # For Each loop
The `foreach` loop is reserved for iterating over containers, and is shorter than its equivalent `for` loop.

```lang=csharp, name=For Each
var myArray = Array[Integer]();
var sum = 0;
for (var i = 0; i < 3; ++i)
{
  myArray.Add(i);
}
Console.WriteLine(myArray);

foreach (var val in myArray)
{
  sum += val;
  Console.WriteLine(sum);
}
```
```name=Console window
{0, 1, 2}
0
1
3
```

Any array that is *indexable* is also //iteratable//.  The Array container in Zilch can be iterated over as shown in `foreach (var val in myArray)`.  Take note that the index isn't accessable in a `foreach` loop, and that `foreach` should only be used when the order that elements are iterated over isn't relevant.

 # Navigating Loops
There are two ways to exit from a loop.  When the loop condition is evaluated to false, the loop will end.  The other way is to use either `return` or `break`.  As explained on the function page, `return` will exit the current function while `break` will leave the next highest loop.  The following code snippet uses `myArray` from the `For Each` code snippet.

```lang=csharp, name=Break
var target : Integer = 1;
for (var index : Integer = 0; index < myArray.Count; ++index)
{
  if(myArray.Get(index) == target)
  {
    Console.WriteLine(index);
    break;
  }
}
Console.WriteLine("Loop Finished");
```
```name=Console window
1
Loop Finished
```
The above code snippet looks for the index of the value `1` in `myArray`.  The array holds `{0, 1, 2}` from the `For Each` code snippet, so the index of the value `1` is `1`.  Once the `break` statement is reached, Zilch will jump directly to the final `}`.  This is the closing brace of the `for` loop block.

 ## Nested Loops
Any loop inside another loop is considered nested.  Be aware in these situations that `break` will exit out of only one loop, while `return` will leave all of them.

```lang=csharp, name=Break
for (var i = 0; i < 3; ++i)
{
  for (var j = 0; j < 3; ++j)
  {
    if(j >= i)
      break;
    
    Console.WriteLine("(`i`, `j`)");
  }
}
```
```name=Console window
(1, 0)
(2, 0)
(2, 1)
```
Notice how the `break` statement only exits the inner `for` loop.  The [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/strings.markdown) passed into `Console.WriteLine` will evaluate to `(1, 0)`, `(2, 0)`, and `(2, 1)`.  In other words, the result is printed when `j < i`.

 ## Continue
The `continue` keyword operates similarly to `break`.  While `break` will jump to the end of the loop's scope **and** exit the loop, `continue` will only jump to the end of the loop's scope.
```lang=csharp, name=Continue
for(var i = 0; i < 5; ++i)
{
  if(i == 2)
    continue;
  
  Console.WriteLine(i);
}
```
```name=Console window
0
1
3
4
```
Notice how `Console.WriteLine(i)` executes for each `i` in the range `[0, 4]` with the exception of `2`.  When `i == 2`, `continue` is reached and the next iteration is reached.  Also note that even when using `continue` in a for loop, the iterative statement `++i` is still executed.

 # Condensed Loops
In the case that a loops only contains one statement within its scope (simliar to [ conditionals ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/conditionals.markdown#condensed-conditionals)) then no `{}` brackets are needed.

```name=Single Line Loop, lang=csharp
for(var i = 0; i < 3; ++i)
  Console.WriteLine(i);
  Console.WriteLine("-");
```
```name=Console Ouput
0
1
2
-
```

Here you can see that the second instance of `Console.WriteLine(i);` is only executed once as it falls outside the scope of the for loop.

 # Related Material
 ## Manual
- [functions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown)
- [strings](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/strings.markdown)

 ## Code Reference
- [array_t](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t.markdown) 
  
  
  
  
  
  
  

 