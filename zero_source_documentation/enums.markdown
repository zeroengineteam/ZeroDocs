One problem in C++ is that there is no way to get a stringified name for each value within an enum. This makes it difficult to display enumeration options in a property grid or bind them to script. To solve this problem, we use a `DeclareEnum#` macro that we generate (where # is how many values the enum has):

```
DeclareEnum3(State, Idle, Patrol, Dead);
```

In the above example, we have created an enum with the name `State` and 3 values: `Idle`, `Patrol`, and `Dead`. In C++ this is roughly equivalent to:

```
namespace State
{
  enum Enum
  {
    Idle = 0,
    Patrol = 1,
    Dead = 2
  };
}
```
`Enum` and is wrapped within a namespace. This is because we thought it was beneficial to always refer to an enum via its name, eg `State::Idle` instead of creating a global constant `Idle`. This also means that if you wish to use the type of the enum you must do `State::Enum`. We also have another type which is `State::Type` that is simply just an unsigned integer which is convenient for accepting flags in C++.

If you wish to bind a data member on a class that is an enum, you can use `BindMemberEnumProperty`. There are other variations that may require getters/setters, such as `BindGetSetEnumProperty`, `BindGetEnumProperty`, and `BindCustomGetSetEnumProperty`. Internally, these macros are mostly the same as their normal bind data member or property counterparts, however each of them invokes the macro `BindEnum` at the beginning. `BindEnum` creates the reflection `MetaType` for that enum (once only). For more information see [meta_binding](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_source_documentation/meta_binding.markdown).
 
  
  
  
  
  
  
  

 