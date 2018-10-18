This section covers the basics of memory management in Zilch. Specifically, the topics covered include: [Types of Memory Storage](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown#types-of-memory-storage), [#allocating-memory](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown#allocating-memory), and [#freeing-memory](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown#freeing-memory)

 # Types of Memory Storage
 ## By-Value

There are two main types of storage, `by-value` and `by-reference` (or `by-ref` for short). `By-value` is stored on the local stack and the storage is cleaned up once it goes out of scope. When passed into a function it copies data `by-value`. [Structs](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/structs.markdown) and primitives are `by-value`.

```lang=csharp, name=By-Value Storage in a Struct
struct ByValue
{
    var ID: Integer = 0;
    constructor(guid: Integer)
    {
        this.ID = guid;
    }
     
    [Static]
    function IncrementID(a: ByValue)
    {
        a.ID += 1;
    }
    
    function ToString() : String
    {
        return "ID: `this.ID`\n";
    }
}
```
```name=Usage, lang=csharp
// If we were to test it:
var byValA: ByValue = local ByValue(1111111);
      
Console.Write("byValA ");
Console.WriteLine(byValA.ToString());           // byValA ID: 1111111
                                                  // by-value copy does not update the passed in argument.
ByValue.IncrementID(byValA);                    // Since it was copied, the changes were to a 
                                                  // local variable. The local variable is destroyed at 
Console.Write("byValA ");                       // the end of the function's scope.
Console.WriteLine(byValA.ToString());           // byValA ID: 1111111
```
```name=Console Window
byValA
ID: 1111111

byValA
ID: 1111111
```

 ## By-Reference
`By-reference` is stored on the heap and the storage is cleaned up once there are no longer references to it, or the handle is explicitly deleted in code. When passed into a [function](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown) it copies it `by-reference`. [Classes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown) and structs promoted with the `ref` keyword are `by-reference`.

 ### By-Ref Storage in a Struct and a Class

```lang=csharp, name=ByValue
struct ByValue
{
    var ID: Integer = 0;
    constructor(guid: Integer)
    {
        this.ID = guid;
    }

    [Static]
    function IncrementID(a: ref ByValue)
    {
        a.ID += 1;
    }
      
    function ToString() : String
    {
        return "ID: `this.ID`\n";
    }
}
```
```name=ByRef
class ByRef
{
    var ID: Integer = 0;
    constructor(guid: Integer)
    {
        this.ID = guid;
    }

    [Static]
    function IncrementID(a: ByRef)
    {
        a.ID += 1;
    }
      
    function ToString() : String
    {
        return "ID: `this.ID`\n";
    }
}
```
```name=Usage, lang=csharp
// If we were to test ByValue:
var byValC: ref ByValue = new ByValue(3333333);
  
Console.Write("byValC ");
Console.WriteLine(byValC.ToString());           // byValC ID: 3333333
  
ByValue.IncrementID(byValC);
                                                // Similar to a pointer, by-ref argument allows for
Console.Write("byValC ");                       // persistent changes to its internals:
Console.WriteLine(byValC.ToString());           // byValC ID: 3333334

// If we were to test ByRef:
var byRefA: ByRef = new ByRef(5555555);
      
Console.Write("byRefA ");
Console.WriteLine(byRefA.ToString());           // byRefA ID: 5555555
  
ByRef.IncrementID(byRefA);                      // Since classes are made to be passed by-reference
                                                  // this works without adding the ref keyword
Console.Write("byRefA ");                       // (adding it would make it not compile!)
Console.WriteLine(byRefA.ToString());           // byRefA ID: 5555556 
```
```name=Console Window
byValC 
ID: 3333333

byValC 
ID: 3333334

byRefA 
ID: 5555555

byRefA 
ID: 5555556
```

 # Allocating Memory

 ## Null

Null is a special type of its own:

```name=null, lang=csharp
Console.Write(typeid(null).Name);  // Null
```

NOTE: A `by-ref` type can be set to null, but a `by-value` type cannot.


 ## Creating variables `by-value` and `by-ref`
 ### Local
When working with by-value types that have constructors, such as structs or more complex stack primitive data types, the [keyword](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown) **local** may be used:

```lang=csharp
var up: Real3 = local Real3(0.0, 1.0, 0.0);
var stackStructInstance: CustomStruct = local CustomStruct();
```

The compiler will infer the use of local for by-value types:
```lang=csharp
// This is also valid.
var up: Real3 = Real3(0.0, 1.0, 0.0);
var stackStructInstance: CustomStruct = CustomStruct();
```

 ### New

When working with classes, references, or other or anything located on the heap with a constructor, use the **new** keyword:

```lang=csharp
var heapObject: CustomClass = new CustomClass();
var heapStructInstance: ref CustomStruct = new CustomStruct();
```

Once again the compiler will infer the use of new for by-ref types:

```lang=csharp
// This is also valid.
var heapObject: CustomClass = CustomClass();
```

Since structs are by-value, in order to get a ref you **must** specify new.

```lang=csharp
// This does not compile
var heapStructInstance: ref CustomStruct = CustomStruct();
```

```name=Console Window
The value being assigned to 'heapStructInstance' must be of type 'ref CustomStruct'. Its type is 'CustomStruct'.
```
-------------

IMPORTANT: Zilch does not currently have a dereferencing operator. Although you can still use the `ref` type with the **dot operator** to access functionality, those typed with `ref` will not be equivalent to the `non-ref` type. *Anything expecting a// `non-ref` //type will not accept a// `ref` //type without dereferencing.* Consider the following:

```lang=csharp, name=Incorrect Assignment of Ref Type to Non-Ref Type
var heapObject: ref CustomStruct = new CustomStruct();
// The following will not compile because they are different types:
//              CustomStruct != ref CustomStruct
var stackObject: CustomStruct = heapObject;
```

 ## constructors

Constructors are required when calling local or new. The only times you wouldn't have a constructor is when your class or struct lacks instanced data, or you are using a primitive data type that can be created from a literal.

```lang=csharp
class MyClass
{
  constructor()
  {
    // Initialize members here.
  }
}
```

A class or struct may possess one or more constructors. Like [functions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown) they can be overloaded via their [named_parameters](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/named_parameters.markdown). Special syntax is also used when constructing a derived class, see [inheritance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/inheritance.markdown) for more.

 # Freeing Memory

Zilch does not have a full-fledged garbage collector, but it does have ref-counted handles. When you use local to make things on the stack they are cleaned up upon leaving the scope. When you use new to construct objects on the heap they are cleaned up when:

 - You call delete on the handle.

 - No references to the object exist.

 ## Important things to note:

1. Zilch **cannot** detect cycles. These must be deleted explicitly.

```lang=csharp, name=Deleting Objects
  // Cycles will not get cleaned up without explicitly deleting.
  var gh: ARefHolder = new ARefHolder("gh");
  var ef: ARefHolder = new ARefHolder("ef");
  // Simply having one point at another is not
  // a cycle, it cleans up just fine.
  gh.Handle = ef; // Both gh & ef will clean up at the end of the scope.
  
  var ab: ARefHolder = new ARefHolder("ab");
  var ba: ARefHolder = new ARefHolder("ba");
  
  ab.Handle = ba;
  ba.Handle = ab;
  Console.WriteLine("Note ba's handle is valid: `ba.Handle`");
  
  // Cleans up when you explicitly delete one of the 
  // Objects as it becomes null and nulls all references
  // to it as ARefHolder is a ZilchType.
  delete ab;
  Console.WriteLine("Note ba's handle has been made null: `ba.Handle`");
  
  var cd: ARefHolder = new ARefHolder("cd");
  var dc: ARefHolder = new ARefHolder("dc");
  
  cd.Handle = dc;
  dc.Handle = cd;
  
  // Making a reference type null does not delete it. 
  // The object is still alive in dc's handle
  // and since that handle has an object that refers 
  // back to it; the cycle remains uncollected. (memory leak)
  cd = null;
  
  var ij: ARefHolder = new ARefHolder("ij");
  var ji: ARefHolder = new ARefHolder("ji");
  
  ij.Handle = ji;
  ji.Handle = ij;
  
  // Making null the cyclic handle breaks the cycle
  // allowing ref-counting to take care of the clean up:
  ij.Handle = null;
  
  
  var abc: ARefHolder = new ARefHolder("abc");
  var bca: ARefHolder = new ARefHolder("bca");
  var cab: ARefHolder = new ARefHolder("cab");
  
  abc.Handle = bca;
  bca.Handle = cab;
  cab.Handle = abc;
  // Without deleting any of the objects
  // e.g. delete abc;
  // or breaking the cycle
  // e.g. abc.Handle = null;
  // abc, bca, and cab will leak.
```

2. [delegates](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/delegates.markdown) containing an instance member function hold the `this` handle to the object, and thus will keep ref-counted objects alive.
```lang=csharp, name=Examples of Delegate Leaking
class Utility
{
  [Static]
  function NullDelegate()
  {
  }
}

class DelegateHolder
{
  var Name:String = "Unnamed";
  var Greeting: delegate() = Utility.NullDelegate;
  
  constructor(name: String)
  {
    this.Name = name;
  }
  
  function Introduce()
  {
    Console.WriteLine("Hi I'm `this.Name`");
  }
  
  destructor()
  {
    onsole.WriteLine("Dtor: `this.Name`");
  }
}

class Driver
{
  function DelegateLeaking()
  {
    // Here are five Objects with the ability to hold delegates:
    var leaky = new DelegateHolder("Leaky");
    var tarp = new DelegateHolder("Tarp");
    var waterproof = new DelegateHolder("Waterproof");
    var mop = new DelegateHolder("Mop");
    var morph = new DelegateHolder("Morph");
    
    // This one has another object's delegate.
    // There is no cycle so they are all cleaned up
    // via ref-counting at the end of the scope.
    tarp.Greeting = waterproof.Introduce;
    
    // This instance holds a delegate to its own function. 
    // The delegate, referring to a member function, includes
    // a handle to the instance it is associated with.
    // This creates a cycle between the delegate and the 
    // the instance.
    leaky.Greeting = leaky.Introduce; // This will leak. 
    mop.Greeting = mop.Introduce;
    morph.Greeting = morph.Introduce;

    // To not leak you'd have to either manually delete: 
    delete mop;

    // or break the cycle by changing
    // what the delegate points to:
    morph.Greeting = tarp.Introduce;
    
    // Upon completion the console prints out:
    // Dtor: Mop
    // Dtor: Morph
    // Dtor: Tarp
    // Dtor: Waterproof
    // The Dtor for Leaky is never called; it is a
    // memory leak in this snippet.   
  }
}
```

 ## Deleting variables

```lang=csharp, name=Utility
// Using ByValue and ByRef as defined above & the Utility class:
class Utility
{
  [Static]
  function SafeToString(a: ref ByValue, name: String)
  {
    Console.Write(name);
    if (a == null)
    {
      Console.WriteLine(" is null");
    }
    else
    {
      Console.WriteLine(a.ToString());
    }
  }
  
  [Static]
  function SafeToString(a: ByRef, name: String)
  {
    Console.Write(name);
    if (a == null)
    {
      Console.WriteLine(" is null");
    }
    else
    {
      Console.WriteLine(a.ToString());
    }
  }
}
```

```name=Examples of Deleting Variables, lang=csharp
// Examples of deleting:

// 1. Delete a by-value struct instance:
var byValA: ByValue = local ByValue(1111111);
// Unable to delete a non reference type;
delete byValA; // This line won't compile.

// 2. Delete an instance of a struct promoted to by-reference:
var byValB: ref ByValue = new ByValue(1111111);
var byValC: ref ByValue = byValB;
var byValD: ref ByValue = byValB;
var byValK: ref ByValue = byValC;

// Utility function calls ToString method, when ref is valid.
// If invalid, it indicates it is null.
Utility.SafeToString(byValB, "byValB");  // byValBID: 1111111
Utility.SafeToString(byValC, "byValC");  // byValCID: 1111111
Utility.SafeToString(byValD, "byValD");  // byValDID: 1111111
Utility.SafeToString(byValK, "byValK");  // byValKID: 1111111

// Simply use the delete keyword on the handle.
delete byValB; 
// Since these are all handles to ZilchTypes, all references
// are made null.
Utility.SafeToString(byValB, "byValB");  // byValB is null
Utility.SafeToString(byValC, "byValC");  // byValC is null
Utility.SafeToString(byValD, "byValD");  // byValD is null
Utility.SafeToString(byValK, "byValK");  // byValK is null

// 3. Delete an instance of a class:
var byRefA: ByRef = new ByRef(22222222);
var byRefB: ByRef = byRefA;
var byRefC: ByRef = byRefA;
var byRefK: ByRef = byRefC;

Utility.SafeToString(byRefA, "byRefA");  // byRefAID: 22222222
Utility.SafeToString(byRefB, "byRefB");  // byRefBID: 22222222
Utility.SafeToString(byRefC, "byRefC");  // byRefCID: 22222222
Utility.SafeToString(byRefK, "byRefK");  // byRefKID: 22222222

delete byRefA;

// Since these are all handles to ZilchTypes, all references
// are made null.
Utility.SafeToString(byRefA, "byRefA");  // byRefA is null
Utility.SafeToString(byRefB, "byRefB");  // byRefB is null
Utility.SafeToString(byRefC, "byRefC");  // byRefC is null
Utility.SafeToString(byRefK, "byRefK");  // byRefK is null
```

 ### Important things to note:

1. Zilch **always** sets the deleted handle to null after deletion. Only if the handle points to a *ZilchType// does it make null the other objects referencing it. It //cannot* automatically do things for objects bound through C++. In order to have C++ BoundTypes work the same as ZilchTypes it must be handled in C++ by the object bound. 

2. Deleting in Zilch forwards delete calls to C++ bound objects. Thus, when you call delete in Zilch on a C++ BoundType, that bound type will have the C++ delete called allowing it to call its destructor.

 ## Destructors

```lang=csharp
class MyClass
{
  constructor()
  {
    // Initialize members here.
  }
  
  destructor()
  {
    // Do any object clean-up here.
  }
}
```
Destructors allow you to do any necessary clean up on your part, such as free memory. You can only have one, and there are no parameters or return values. It's important to know that stack allocated instances (i.e. non-ref `by-value` types, or non-ref primitives) have no guarantee they'll call the destructor. Only those objects with handles that do not leak are guaranteed to have their destructors called. 

 # Related Materials
 ## Manual
- [Classes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/classes.markdown)
- [Structs](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/structs.markdown)
- [Functions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown)
- [Keywords](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/keywords.markdown)
- [named_parameters](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/named_parameters.markdown)
- [inheritance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/inheritance.markdown)
- [delegates](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/delegates.markdown) 
  
  
  
  
  
  
  

 