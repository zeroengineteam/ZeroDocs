
 # Learning Objectives
- Drawing debug primitives

Often when developing a game we may we run into data that is hard to interpret from just printing to the [console](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/console.markdown). Values such as [Velocity](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown#velocity-zero-engine-doc) or the direction a [ Cog ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown) is facing are better represented visually than by numerical values. DebugDraw objects are a useful debuging technique that allows us to draw simple primitives to visually represent data in the game itself.

 # Level Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateCube](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createcube)
- In the `Properties Window`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, -2, 0]`
  - Set Scale  to `[20, 1, 1]`
- [ Remove Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `DebugLauncher`

- Update the `DebugLauncher` class to the following:
```name=DebugLauncher, lang=csharp
class DebugLauncher : ZilchComponent
{
  [Dependency] var RigidBody : RigidBody;
  [Dependency] var Transform : Transform;
  
  [Property]
  var Camera : CogPath = CogPath();
  
  var Drawing : Boolean = false;
  
  var Target : Real3;
  
  var TargetLine : DebugLine = DebugLine();
  
  function Initialize(init : CogInitializer)
  {
    this.TargetLine.Color = Colors.Red;
    Zero.Connect(this.Space, Events.MouseDown, this.OnMouseDown);
    Zero.Connect(this.Space, Events.MouseUp, this.OnMouseUp);
    Zero.Connect(this.Space, Events.FrameUpdate, this.OnFrameUpdate);
  }

  function OnMouseDown(event : ViewportMouseEvent)
  {
    Console.WriteLine("Drawing");
    this.Drawing = true;
  }

  function OnMouseUp(event : ViewportMouseEvent)
  {
    Console.WriteLine("Not Drawing");
    this.Drawing = false;
    this.RigidBody.Velocity = this.Target - this.Transform.Translation;
  }

  function OnFrameUpdate(event : UpdateEvent)
  {
    if(!this.Drawing)
      return;
    
    var mouseScreenPos = Zero.Mouse.ClientPosition;
    var mouseWorldPos = this.Camera.CameraViewport.ScreenToWorldZPlane(mouseScreenPos, 0.0);
    this.Target = mouseWorldPos;
  }
}
```

Notice we use [FrameUpdate](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#frameupdate) as opposed to [LogicUpdate](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#logicupdate). Generally, debug drawing should still occur when a [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown) is paused, and FrameUpdate is sent every frame, whether a space is paused or not. 

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSphere](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsphere)
- [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `DebugLauncher`
- In the `Properties Window`
 - Under `DebugLauncher`
  - Set Camera  to GameCamera object
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- `Click + Hold` and `Release` around on the screen above the platform



![DebugLauncher](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/98966.gif)


NOTE: The yellow circle overlaying the cursor is added to the image by the screen-capture program after it is captured to indicate when the mouse button is down.

We can see when the mouse button is released that the velocity of the ball is set and the ball launches towards the cursor position. This is a prime example of a physics-based behavior that can be hard to debug or tune without further visual assistance.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 # DebugLine
One of the most common debug draw type is [DebugLine](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugline.markdown), which is actually a line segment as it has start and end points. 

- Add the following to the `DebugLauncher` class:

```name=DrawDebug Function, lang=csharp
function DrawDebug()
{
  this.TargetLine.Start = this.Transform.Translation;
  this.TargetLine.End = this.Target;
  DebugDraw.Add(this.TargetLine);
}
```

Here we configure the debug line for the current frame by setting a start and end point for the segment. The final line of code `DebugDraw.Add(this.TargetLine);` adds `this.TargetLine` to a list of debug objects which should be drawn that frame. This means that debug object must be passed to [DebugDraw.Add](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugdraw.markdown#add-void-k) each frame they should be drawn.

- Add the following to the `OnFrameUpdate` function in the `DebugLauncher` class:

```name=Adding DrawDebug to OnFrameUpdate, lang=csharp
this.DrawDebug();
```

Calling our `DrawDebug` function every frame that the mouse is down allows our drawing of the line segment to be reactive to when we want to communicate the information about the launch velocity. Integrating debug drawing into functionality you are implementing is a fairly common task.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- `Click + Hold` and `Release` around on the screen above the platform



![DebugLauncherDraw](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/98968.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 # DebugCircle
There are many types that can be debug drawn, as can be seen in the [Related Materials](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/scripting/debugdrawing/.markdown#related_materials)[DebugCircle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcircle.markdown), which will be used to make a clock.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `DebugClock`
- Update the `DebugClock` class to the following:
```name=DebugClock, lang=csharp
class DebugClock : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var ClockRadius : Real = 5.0;
  
  var Circle : DebugCircle = DebugCircle();
  
  function Initialize(init : CogInitializer)
  {
    this.Circle.Position = this.Transform.Translation;
    this.Circle.Radius = this.ClockRadius;
    this.Circle.Color = Colors.Blue;
    
    Zero.Connect(this.Space, Events.FrameUpdate, this.OnFrameUpdate);
  }

  function OnFrameUpdate(event : UpdateEvent)
  {
    this.DrawClockFrame();
  }
  
  function DrawClockFrame()
  {
    DebugDraw.Add(this.Circle);
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateTransform](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createtransform)
- [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `DebugClock`


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/98979.png)


We can see the [DebugCircle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcircle.markdown) being drawn in the background now. Just like we set the color of the line we can set the color of the circle. 

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

- Add the following to the `DebugClock` class:
```name=New DebugClock Variables, lang=csharp
[Property]
var SecondHandRadius : Real = 3.0;

[Property]
var MinuteHandRadius : Real = 4.0;

[Property]
var StartAngleOffset : Real = 90.0;

[Property]
var CounterClockWise : Boolean = false;

var MinuteHand : DebugLine = DebugLine();
var SecondHand : DebugLine = DebugLine();

var Timer : Real = 0.0;
var Minutes : Real = 0;
var Seconds : Real = 0;
```

Here we define the data necessary to draw the hands of the clock.

- Replace the `Initialize` function in the `DebugClock` class with the following: 
```name=DebugClock.Initialize, lang=csharp
function Initialize(init : CogInitializer)
{
  this.SecondHand.Start = this.Transform.Translation;
  this.SecondHand.Color = Colors.Red;
  this.MinuteHand.Start = this.Transform.Translation;
  this.MinuteHand.Color = Colors.Green;
  this.Circle.Position = this.Transform.Translation;
  this.Circle.Radius = this.ClockRadius;
  this.Circle.Color = Colors.Blue;
  
  Zero.Connect(this.Space, Events.FrameUpdate, this.OnFrameUpdate);
}
```
Unlike the `DebugLauncher` the start position of the lines are not changing so we can set up the start position of all the debug elements in `Initialize`. Now that the initial data has been defined let's implement the calculations for the rest or the line data.

- Add the following to the functions in the `DebugClock` class:
```name=DebugDraw Functions, lang=csharp
function DrawSecondHand()
{
  //Calculate what percentage of the current minute has passed
  this.Seconds = this.Timer % 60.0;
  var percCurrentMin = this.Seconds / 60.0;
  
  //Calculate the angle of the seconds hand
  var angle = (2*Math.Pi) * percCurrentMin;
  if(!this.CounterClockWise)
    angle *= -1.0;
  
  //Offset the starting angle so the hand starts at the top of the clock
  angle += Math.ToRadians(this.StartAngleOffset);
  var dir = Real3(Math.Cos(angle), Math.Sin(angle), 0.0);
  
  //Calculate the endpoint of the seconds hand line segment based off the calculated angle
  this.SecondHand.End = this.Transform.Translation + (dir * this.SecondHandRadius);
  DebugDraw.Add(this.SecondHand);
}

function DrawMinuteHand()
{
  //Calculate what percentage of the current hour has passed
  this.Minutes = this.Timer / 60.0;
  var perc = this.Minutes / 60.0;
  
  //Calculate the angle of the minutes hand
  var angle = (2*Math.Pi) * perc;
  if(!this.CounterClockWise)
    angle *= -1.0;
  
  //Offset the starting angle so the hand starts at the top of the clock
  angle += Math.ToRadians(this.StartAngleOffset);
  var dir = Real3(Math.Cos(angle), Math.Sin(angle), 0.0);
  
  //Calculate the endpoint of the minute hand line segment based off the calculated angle
  this.MinuteHand.End = this.Transform.Translation + (dir * this.MinuteHandRadius);
  DebugDraw.Add(this.MinuteHand);
}
```

Every frame we need to call the function we just wrote to draw each part of the clock as well as increment the timer.

- Replace the `OnFrameUpdate` function in the `DebugClock` class with the following: 
```name=DebugClock.OnFrameUpdate, lang=csharp
function OnFrameUpdate(event : UpdateEvent)
{
  this.DrawSecondHand();
  this.DrawMinuteHand();
  this.DrawClockFrame();
  this.Timer += event.Dt;
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)

- Watch the clock



![Clock1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/98981.gif)



![Clock2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/98983.gif)


*Here we see the clock in motion at different point in it's cycle*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

Now we know how to debug draw simple objects. Let's look at a more complicated built-in example.

 # VortexEffect

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateTransform](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createtransform)
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [VortexEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/vortexeffect.markdown)
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0,5,0]`
 - Under [VortexEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/vortexeffect.markdown)
  - Set VortexAxis  to `[0,0,1]`



![VortexEffect](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101956.gif)


Here is an example of a built-in debug draw effect in action. You actually see debug drawing everytime you use and editor tool; PhysicsEffect components just offer a more complex example. In the case of the [VortexEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/vortexeffect.markdown) multiple [DebugArc](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugarc.markdown) objects are drawn indicating the direction and speed of the vortex, while [DebugLine](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugline.markdown) objects are used to show that the component is pulling objects into the vortex as opposed to throwing them out.

 # Related Materials
 ## Manual
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
- [ Remove Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)

 ## Tutorial
- [PhysicsEffects](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/physics/physicseffects.markdown)

 ## Reference
 ### Classes
- [ Cog ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)
- [Console](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/console.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
- [DebugArc](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugarc.markdown)
- [DebugBox](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown)
- [DebugCapsule](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcapsule.markdown)
- [DebugCircle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcircle.markdown)
- [DebugCone](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcone.markdown)
- [DebugCylinder](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown)
- [DebugFrustum](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugfrustum.markdown)
- [DebugLine](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugline.markdown)
- [DebugLineCross](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debuglinecross.markdown)
- [DebugObb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugobb.markdown)
- [DebugSphere](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugsphere.markdown)
- [DebugText](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugtext.markdown)
- [DebugTriangle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugtriangle.markdown)
- [VortexEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/vortexeffect.markdown)

 ### Commands
- [ New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
- [ CreateTransform](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createtransform)
- [ CreateCube](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createcube)

- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 ## Development Task
- T1343 

 