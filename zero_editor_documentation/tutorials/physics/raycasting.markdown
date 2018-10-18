This lesson covers how to cast rays using Physics and interpret the results.


 # Learning Objectives

- Understanding rays, lines, and line segments
- Learning how to cast various geometric primitives
- Learning how to interpret and use the results of a cast

 # Level Setup

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Square`
 - Under [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[-4, 0, 0]`

 - Create three sprite objects with the following properties:

| Name | `Transform>Translation` | `Sprite>VertexColor` | `Sprite>SpriteSource` |
|------------|---|---|---|
| RedCircle object     | `[-1.5, 0, 0]`| `[R:255, G:0, B:0, A:1.00]`| `Circle` |
| GreenCircle object  | `[0, 0, 0]`| `[R:0, G:255, B:0, A:1.00]` | `Circle` |
| BlueCircle object  | `[1.5, 0, 0]`| `[R:0, G:0, B:255, A:1.00]` | `Circle` |



![RaycastSetup](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/104850.png)


*The property values should look like this*


- - [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `MoveUpAndDown`
- In the `MoveUpAndDown` script
 - Update the `MoveUpAndDown` class to the following:

```lang=csharp, name="MoveUpAndDown"
class MoveUpAndDown : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property] 
  var StartPosition : Real3 = Real3(0,1,0);
  
  [Property] 
  var EndPosition : Real3 = Real3(0,-1,0);
  
  [Property]
  var MoveDuration : Real = 1.0;
  
  function Initialize(init : CogInitializer)
  {
    this.Transform.Translation = this.StartPosition;
    this.MoveToEnd();
  }
  
  function MoveToEnd()
  {
    var seq = Actions.Sequence(this.Owner.Actions);
    Actions.Property(seq, @this.Transform.Translation, this.EndPosition, this.MoveDuration, Ease.Linear);
    Actions.Call(seq, this.MoveToStart);
  }
  
  function MoveToStart()
  {
    var seq = Actions.Sequence(this.Owner.Actions);
    Actions.Property(seq, @this.Transform.Translation, this.StartPosition, this.MoveDuration, Ease.Linear);
    Actions.Call(seq, this.MoveToEnd);
  }
}
```

- For each Circle object
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [spherecollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spherecollider.markdown)
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
 - Under [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
  - Set DynamicState enum to `Kinematic`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `MoveUpAndDown`
 - Under `MoveUpAndDown`
  - Set the properties to the following:

|  Name |  StartPosition |  EndPosition |  MoveDuration  |
|--------|---------------|---------------|-----------------|
| RedCircle object | `[-1.5, 1, 0]` | `[-1.5, -1, 0]` | `1` |
| GreenCricle object | `[0, 1, 0]` | `[0, -1, 0]` | `2` |
| BlueCircle object | `[1.5, 1, 0]` | `[1.5, -1, 0]` | `3` |


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![RaycastSetup](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/105498.gif)

 *The circles should move like this*

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)


 # Rays

A ray is a portion of a line that starts at a given location and extends infinitely far in a given direction. In Zero Engine, you can create rays and cast them in order to find what it intersects with. This can be used for a variety of applications, including:

 - Simulating laser beams
 - Simulating high velocity projectiles
 - Checking for line of sight
 - Detecting walls
 - Detecting distance to an object

NOTE:
  It's worth noting the difference between rays, segments and lines. Rays are infinitely long, defined by a start point and a direction. Segments are defined by a start and end point. Lines are defined by two points and extend infinitely.
  ![Ray](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/104865.gif) ![Segment](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/104867.gif) ![Line](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/104869.gif)

 # Creating and Casting

The first step to raycasting is to build the ray with the desired parameters. Let's take a look.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `RayCasterLogic`
- In the `RayCasterLogic` script
 - Update the `RayCasterLogic` class to the following:

```lang=csharp, name="Ray Casting"
class RayCasterLogic : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var Direction : Real3 = Real3(1.0, 0.0, 0.0);
  
  [Property]
  var DebugDrawOn : Boolean = true;
  
  [Property]
  var MaxDebugLineLength : Real = 8.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    this.FindFirstObject();
  }
  
  function FindFirstObject()
  {
    //Create ray
    var ray = Ray();
    ray.Start = this.Transform.Translation;
    ray.Direction = this.Direction;
    
    //Cast ray
    var result = this.Space.PhysicsSpace.CastRayFirst(ray);
    
    //Interpret results
    if(result.ObjectHit != null)
    {
      //Set our owner's color to match the color of the object we hit
      this.Owner.Sprite.VertexColor = result.ObjectHit.Sprite.VertexColor;
      Console.WriteLine("Ray found: `result.ObjectHit.Name`");
    }
    else
    {
      //If no objects were hit, set our owner's color to white
      this.Owner.Sprite.VertexColor = Colors.White;
      Console.WriteLine("No object found!");
    }
    
    //Visual Debug
    if(this.DebugDrawOn)
    {
      var debugRay = DebugLine();
      debugRay.Start = ray.Start;
      debugRay.End = ray.Start + Real3.XAxis * Math.Min(result.Distance, this.MaxDebugLineLength);
      debugRay.HeadSize = 0.2;
      DebugDraw.Add(debugRay);
    }   
  }
}
```
- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Square object
- In the `Properties Window`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `RaycasterLogic`

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![RaycastFirst](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/105501.gif)


*We can see the ray starting at the Square object and extending to the right. Upon intersecting with one of the circles, the color of the square is changed to match it.*


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)



Raycasting always consists of 3 steps:

1. Create the [Ray](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Ray.markdown)
2. Request the [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown) to cast it (storing the results)
3. Interpret the [CastResult](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastResult.markdown)

If the ray intersects an object, you can retrieve the following information from the [CastResult](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastResult.markdown):

|CastResult |
|------------|
| Collider | The collider intersected by the ray |
| Distance | Distance from the ray start to the point of intersection|
| ObjectHit | The cog hit by the cast|
| Normal | The normal of the surface at the intersection point |
| WorldPosition |World-space position where the object was hit|

 # Multiple Results

It is also possible to cast a Ray and retrieve the resulting intersections with multiple objects by using the [ PhysicsSpace.CastRay()](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown) function instead.

- Add the following function to the `RayCasterLogic` class:

```lang=csharp, name="Multiple Results"
  function FindSeveralObjects()
  {
    //Create Ray
    var ray = Ray();
    ray.Start = this.Transform.Translation;
    ray.Direction = this.Direction;
    
    //Cast Ray
    var results = this.Space.PhysicsSpace.CastRay(ray, 3);
    
    this.Owner.Sprite.VertexColor = Real4(0,0,0,1);
    
    //Interpret Results
    foreach(var result in results)
    {
      //If the object has a sprite component
      if(result.ObjectHit.Sprite != null)
      {
        //Add that object's color to our owner's color
        this.Owner.Sprite.VertexColor += result.ObjectHit.Sprite.VertexColor;
      }
    }
    
    //Visual Debug
    if(this.DebugDrawOn)
    {
      var debugRay = DebugLine();
      debugRay.Start = ray.Start;
      debugRay.End = ray.Start + Real3.XAxis * this.MaxDebugLineLength;
      debugRay.HeadSize = 0.2;
      DebugDraw.Add(debugRay);
    }
  }
```

- Replace the `OnLogicUpdate` function in the `RayCasterLogic` class with the following:

```lang=csharp, name="New Logic Update"
  function OnLogicUpdate(event : UpdateEvent)
  {
      //this.FindFirstObject();
      this.FindSeveralObjects();
  }
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![RaycastMultiple](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/105983.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

The [ CastRay](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown) function allows you to specify the ray and a maximum number of objects to detect. It returns a range of [ CastResults](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastResult.markdown) that contains all of the objects intersected (up to the specified number) in order of distance (closest to farthest).

 # Cast Filters

[ CastFilters](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastFilter.markdown) allow you to customize which objects the raycast process should hit and which should be ignored. The filter can then be passed as an optional third parameter to the `CastRay` function.

- Replace the `FindSeveralObjects` function in the `RayCasterLogic` class with the following :

```lang=csharp, name="Filter Example"
  function FindSeveralObjects()
  {
    //Create Filter
    var filter = CastFilter();
    filter.IgnoreGhost = true;
    
    //Create Ray
    var ray = Ray();
    ray.Start = this.Transform.Translation;
    ray.Direction = this.Direction;
    
    //Cast Ray
    var results = this.Space.PhysicsSpace.CastRay(ray, 3, filter);
    
    this.Owner.Sprite.VertexColor = Real4(0,0,0,1);
    
    //Interpret Results
    foreach(var result in results)
    {
      //If the object has a sprite component
      if(result.ObjectHit.Sprite != null)
      {
        //Add that object's color to our owner's color
        this.Owner.Sprite.VertexColor += result.ObjectHit.Sprite.VertexColor;
      }
    }
    
    //Visual Debug
    if(this.DebugDrawOn)
    {
      var debugRay = DebugLine();
      debugRay.Start = ray.Start;
      debugRay.End = ray.Start + Real3.XAxis * this.MaxDebugLineLength;
      debugRay.HeadSize = 0.2;
      DebugDraw.Add(debugRay);
    }
  }
```

- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : GreenCircle object
- In the `Properties Window`
 - Under [SphereCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/SphereCollider.markdown)
  - Set  Ghost checkBox to `true`

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![RaycastMultipleFiltered](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/105986.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

Here are some useful properties you can set on the [CastFilter](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastFilter.markdown) that allow you to further customize which objects to ignore.

|Cast Filter|
|-----------|
|IgnoreCog| [Cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Cog.markdown)| A given specific Cog to ignore |
|IgnoreDynamic| [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| Ignores all objects marked as [Dynamic](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate)|
|IgnoreGhost| [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| Ignores all objects marked as [Ghost](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collider.markdown#ghost)|
|IgnoreKinematic| [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| Ignores all objects marked as [Kinematic](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate)|
|IgnoreStatic| [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| Ignores all objects marked as [Static](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate)|
|CollisionGroup| [collisiongroup](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisiongroup.markdown)| Makes the Ray behave as part of a collision group, using the current [collisiontable](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisiontable.markdown) |



 # Other Types of Casting

In addition to Rays, Zero Engine allows you to cast other types of shapes, including:

- [Segment](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Segment.markdown)
- [Sphere](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Sphere.markdown)
- [Aabb](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Aabb.markdown)
- [Frustum](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Frustum.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown)

They all follow the same basic steps described in this tutorial: define the shape, request [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown) to cast it (with the optional inclusion of a [CastFilter](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastFilter.markdown)) and then interpret the results. You can read more about them in the [ PhysicsCasting](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicscasting.markdown) Manual Page.


 # Related Materials

 ## Manual
- [ PhysicsCasting](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicscasting.markdown)
- [ Colliders](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [ Collision Groups and Tables](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview/collisiongroupsandtables.markdown)

 ## Tutorial
- [collisiongroups](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/physics/collision/collisiongroups.markdown)


 ## Code Reference
 ### Classes
- [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Transform.markdown)
- [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Sprite.markdown)
- [Cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Cog.markdown)
- [spherecollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spherecollider.markdown)
- [Ray](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Ray.markdown)
- [Segment](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Segment.markdown)
- [CastFilter](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastFilter.markdown)
- [CastResult](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/CastResult.markdown)
- [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsSpace.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown)
- [collisiongroup](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisiongroup.markdown)
- [collisiontable](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisiontable.markdown)
- [sphere](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sphere.markdown)
- [aabb](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/aabb.markdown)
- [frustum](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/frustum.markdown)

 ## Enums
- [RigidBodyDynamicState](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#rigidbodydynamicstate)

 ### Commands
- [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)


 ## Development Task
- T1188 
  
  
  
  
  
  
  

 