The [orientation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown) component is a utility component that helps makes the manipulation of the transform of an object easier. It can be particularly useful when an object has its own sense of forward (for example where a person or a spaceship is facing).

 # Configuring Orientation
The first step after attaching an Orientation component to an object is to configure the orientation basis. By redefining forward, up, and right for an object, many calculations of finding those values at runtime can be avoided later. In the image below a cube can be seen with the default orientation values. The blue arrow is the `WorldForward`, the green arrow is the `WorldUp`, and the red arrow is the `WorldRight` of the cube.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47526.png)


The cube has defined the `-Z` axis as its `LocalForward` and the `+Y` axis as its `LocalUp`. This means that its `LocalRight` is the `+X` axis. This can be changed to a number of common presets as scene in the next image.



![5ad9c149-9f8f-4646-aacd-cf838d759c86](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47532.gif)


*The built in Orientation presets.*


Occasionally, an object's default rotation does not align with any World axis, making all the built in Orientation presets unusable. In cases such as these it is possible to manually define the orientation bases by rotation.



![ce0d6555-e050-4fc3-a535-86c2ae6a5826](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47534.gif)


*Defining a custom Orientation Bases.*


The Orientation component calculates the WorldDirections from its LocalDirection Properties by applying the object's Rotation.



![c4cd957d-06d4-4c28-b8d2-dd386755a1ef](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47530.gif) *When an Oriented object is rotated, its WorldDirections are rotated with it.*


 # Using Orientation
Oriented directions are helpful in and of themselves. Attaching `Orientation` to a character is an easy way to determine which direction the character is looking at any given moment with out having to calculate it in script. This can come in useful for vision checks, aligning two objects, etc.

 ## Look At Functions

- [Orientation.LookAtPoint()](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#lookatpoint-void)
- [Orientation.LookAtDirection()](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#lookatdirection-void)

The most common use of `Orientation` is to make the object face a given point or direction. There are multiple ways to do this in the script below uses the `LookAtPoint` function to make the cube face the mouse position on the world Z-Plane.

```
class LookAtMouse : ZilchComponent
{
  [Dependency]
  var Orientation : Orientation;
  
  [Property]
  var CameraPath : CogPath = CogPath();
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var mousePos = this.CameraPath.Cog.CameraViewport.ScreenToWorldZPlane(Zero.Mouse.ClientPosition, 0.0);
    var debugSphere = DebugSphere(mousePos, 0.1);
    DebugDraw.Add(debugSphere);
    
    this.Orientation.LookAtPoint(mousePos);
  }
}

```




![5989cc9d-d580-41b2-ad47-5bd32e0f3ab9](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47538.gif)


*P576 in rotating the object to face the mouse.*


The same functionality can be achieved with `LookAtDirection` by slightly altering the script.

```
class LookAtMouse : ZilchComponent
{
  [Dependency]
  var Orientation : Orientation;
  
  [Property]
  var CameraPath : CogPath = CogPath();
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var mousePos = this.CameraPath.Cog.CameraViewport.ScreenToWorldZPlane(Zero.Mouse.ClientPosition, 0.0);
    var debugSphere = DebugSphere(mousePos, 0.1);
    DebugDraw.Add(debugSphere);
    
    var direction = Math.Normalize(mousePos - this.Owner.Transform.Translation);
    this.Orientation.LookAtDirection(direction);
  }
}

```


Notice that when the `WorldForward` of the cube rotates past the `Y` axis, its `WorldUp`, the `WorldRight` flips to the other side of the object. This is because typically the `WorldRight` is derived from the cross product of the object's `WorldForward` and `WorldUp`. The orientation component does not care about any previous rotation of the object and `LookAt` functions will always result in a normalized rotation, meaning all Euler Angles will fall in the range [-180.0, 180.0] when `LookAt` functions are used to set an object's `Rotation`. This issue can be fixed by properly setting [Orientation.WorldUp](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#worldup-zero-engine-docu) to `[0,0,1]` to match the [DefaultOrientationBases](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#defaultorientationbases) of the object.

 ## `WithUp...` Functions

- [Orientation.LookAtPointWithUp()](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#lookatpointwithup-void)
- [Orientation.LookAtDirectionWithUp()](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown#lookatdirectionwithup-void)

The `LookAt` functions on `Orientation` each have a corresponding version with `WithUp` appended. These functions let the user define the `WorldUp` to rotate around instead of the objects `WorldUp` defined on the `Orientation` component.

```
class LookAtMouse : ZilchComponent
{
  [Dependency]
  var Orientation : Orientation;
  
  [Property]
  var CameraPath : CogPath = CogPath();
  
  [Property]
  var Up : Real3 = Real3(1,0,0);
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var mousePos = this.CameraPath.Cog.CameraViewport.ScreenToWorldZPlane(Zero.Mouse.ClientPosition, 0.0);
    var debugSphere = DebugSphere(mousePos, 0.1);
    DebugDraw.Add(debugSphere);
    
    var direction = Math.Normalize(mousePos - this.Owner.Transform.Translation);
    this.Orientation.LookAtDirectionWithUp(direction, this.Up);
  }
}

```


In this example `LookAtDirectionwithUp()` was called with and up value of `(1, 0, 0)`. Notice that now the `WorldRight` of the cube now flips when the `WorldForward` crosses over the `X` axis instead of the `Z` axis as before.



![c2dc9d51-7c44-4cf6-a894-5cada4944de7](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47575.gif)


 ## `GetLookAt...Rotation` Functions
While the `LookAt` functions can be very useful, they will often not be smooth enough for gameplay; in such cases, the `GetLookAt` functions must be used. These are "query-only" functions and return the `Quaternion` representing the rotation that the corresponding `LookAt` function would have set `Transform.Rotation` to.

```
class LookAtMouse : ZilchComponent
{
  [Dependency]
  var Transform : Transform;
  
  [Dependency]
  var Orientation : Orientation;
  
  [Property]
  var CameraPath : CogPath = CogPath();
  
  [Property]
  var Up : Real3 = Real3(1,0,0);
  
  [Property]
  var Interpolated : Boolean = true;
  
  [Property]
  var InterpolationSpeed : Real = 1.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var mousePos = this.CameraPath.Cog.CameraViewport.ScreenToWorldZPlane(Zero.Mouse.ClientPosition, 0.0);
    var debugSphere = DebugSphere(mousePos, 0.1);
    DebugDraw.Add(debugSphere);
    
    var direction = Math.Normalize(mousePos - this.Owner.Transform.Translation);
    var targetRotation = this.Orientation.GetLookAtDirectionWithUpRotation(direction, this.Up);
    
    if(this.Interpolated)
    {
      var newRotation = Math.Slerp(this.Transform.Rotation, targetRotation, this.InterpolationSpeed * event.Dt);
      this.Transform.Rotation = newRotation;
    }
    else
      this.Transform.Rotation = targetRotation;
  }
}
```




![test](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47595.gif)


With the cube's `Rotation` being interpolated instead of directly set it is now possible to see the behavior that the flip of `WorldRight` will cause, and it is most often undesirable. However, this flip only occurs because `Up` is set to a value that the `WorldForward` aligns with and then crosses over.

By setting the `Up` axis to be the intended axis of rotation (the world `Z` axis) the cube no longer flips, as the cube's `WorldForward` no longer crosses over the defined `Up` for the rotation.

(WARNING)**Slow Interpolation Speeds**: A common mistake when using `GetLookAt` functions in combination with `Math.Slerp` is to set the interpolation speed to slow. In this case because the mouse has no digital limit on the speed of movement the target rotation of the cube can change much faster than the `InterpolationSpeed` allows the cube's `Rotation` to change. ![SlowInterpolationLookAt](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47597.gif) As shown, due to the normalized rotation values returned by `GetLookAtDirectionWithUpRotation` the cube never makes a full rotation despite the mouse making multiple full rotation around it.

 # Related Materials
 ## Code Reference
- [orientation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/orientation.markdown) 
  
  
  
  
  
  
  

 