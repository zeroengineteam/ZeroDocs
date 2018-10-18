**Swizzling** is accessing the values within vector types ([ Real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown), [ Integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown), etc.) in any order. The term *swizzling* originated as the name for a technique used for doing the same thing, but within shaders.

 # Understanding a Swizzle
To swizzle a vector, refer to its values as if they were data members, using the letters `X`, `Y`, `Z`, and `W` for the corresponding elements. These can be combined in any permutation or combination.

```name=Simple Swizzle, lang=csharp
var a = Real3(0,1,2);
Console.WriteLine("Example 1: a.X: `a.X`");
Console.WriteLine("Example 2: a.XYZ: `a.XYZ`");
Console.WriteLine("Example 3: a.XY: `a.XY`");
Console.WriteLine("Example 4: a.YX: `a.YX`");
Console.WriteLine("Example 5: a.XXY: `a.XXY`");
Console.WriteLine("Example 6: a.ZYXZ: `a.ZYXZ`");
```
```name=Console Output
Example 1: a.X: 0
Example 2: a.XYZ: (0, 1, 2)
Example 3: a.XY: (0, 1)
Example 4: a.YX: (1, 0)
Example 5: a.XXY: (0, 0, 1)
Example 6: a.ZYXZ: (2, 1, 0, 2)
```

In this example `a` is a simple [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown):

- Example 1 constructs a [Real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown) containing the value of `a.X`
- Example 2 constructs a [by-value](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/constructbyvaluevsbyref.markdown) copy of `a`.
- Example 3 constructs a [real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown) containing the `X` and `Y` values of `a`. 
- Example 4 constructs a [real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown) with `X` as the value of `a.Y`, and `Y` as the value of `a.X`.
- Example 5 constructs a [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown) where the `X` and `Y` are set to the value of `a.X` and `Z` is set to the value of `a.Y`.
- Example 6 constructs a [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown) with the same `X`, `Y`, and `Z` values as the original vector `a`, but whose `W` value is the value of `a.Z`.

 # Assigning With Swizzles
Extracting portions of a vector as seen above is a fairly common operation even outside of shader development. An example may be centering the camera object while not affecting its zoom in a 2D game.

```name=XY Assignment Without Swizzle, lang=csharp
//0 out the XY axis and maintain the Z axis values
var cameraOffset = this.Camera.Transform.LocalTranslation;
cameraOffset.XY = Real2.Zero;
this.Camera.Transform.LocalTranslation = cameraOffset;
```
If we tried to assign into the swizzle constructed by-value from the member variable, however, it would not work:

```name=Direct Assignment Into Member Swizzle, lang=csharp, counterexample
this.Camera.Transform.LocalTranslation.XY = Real2();
```

In this example `.XY` returns a by-value copy of the `LocalTranslation`'s `X` and `Y` values as a [Real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown). So in this example when we assign the `Real2()` into it we are assigning into a copy instead of the member variable itself.

 # Related Materials
 ## Manual
- [constructbyvaluevsbyref](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/constructbyvaluevsbyref.markdown)
- [properties](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/properties.markdown)

 ## Reference
- [real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)
- [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)
- [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown)
- [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)

 ## Task
- T950 
  
  
  
  
  
  
  

 