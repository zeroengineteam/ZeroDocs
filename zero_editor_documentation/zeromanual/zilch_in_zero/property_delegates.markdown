Property Delegates can be generated from any field using the `@` symbol. Fields are variables, but not all variables are fields. Local variables do not have the ability to be accessed via a property and they cannot be used in conjunction with the property delegate operator like fields can.

```name=Cat, lang=csharp
class Cat
{
  var Lives: Integer = 9;

  function Example()
  {
    // @, the property delegate operator, takes this.Lives
    // and creates a property delegate from it.
    var prop = @this.Lives;

    Console.WriteLine(typeid(prop).Name); // Property[Integer]
    Console.WriteLine(prop.Get());        // 9

    prop.Set(7);
    Console.WriteLine(prop.Get());        // 7
    Console.WriteLine(this.Lives);        // 7
  }
}
```
```name=Console Output
Property[Integer]
9
7
7
```

 # Property Delegates as Function Parameters
Choosing to take a property delegate as a parameter allows the user to propagate side-effects to the parameters that would otherwise be lost on copies passed in by-value.

```name=PropertyDelegateTest, lang=csharp
class PropertyDelegateTest : ZilchComponent
{
  [Property]
  var MyProperty : Real = 5.0;

  function Initialize(init : CogInitializer)
  {
    Console.WriteLine("Before Drivers: `this.MyProperty`") //
    this.DriverControl(this.MyProperty);
    Console.WriteLine("Between Drivers: `this.MyProperty`")
    this.Driver(@this.MyProperty);
    Console.WriteLine("After Drivers: `this.MyProperty`")
  }

  function Driver(prop : Property[Integer])
  {
    prop.Set(15);
    Console.WriteLine("Inside Driver: `prop.Get()`);
  }

  function DriverControl(prop : Integer)
  {
    prop = 2;
    Console.WriteLine("Inside DriverControl: `prop`);
  }
}
```
```name=Console Output
Before Drivers: 5.0
Inside Driver: 15.0
Between Drivers: 15.0
Inside DriverControl: 2.0
After Drivers: 15.0
```
In this example it can be seen that when the property delegate of `MyProperty` is passed into the function `Driver()` it can be used to set the value of the member variable. This is because desprite the delegate itself being passed by value into the function it still contains a reference to `MyProperty`. However, when `MyProperty` is passed directly into the function `DriverControl()` it is also passed by value. The assignment of `prop` in `DriverControl()` is actually setting the value of the a local copy of `MyProperty`. When the function completes and reaches the end of its scope `prop` will cease to exist.  

 