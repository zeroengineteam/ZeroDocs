Having already seen [spaces](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/architecture/spaces.markdown) in a previous tutorial, we will now talk about a component that only appears on space objects: the [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown).


 #  Learning Objectives


- TimeScale
- Pausing


 #  Level Setup


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/boxcollider.markdown)
 - Under [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
  - Set `name=DynamicState,icon=list` to [Static](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#rigidbodydynamicstate)
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
  - Set Scale  to `[25,1,1]`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSphere](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsphere)
- In the `Properties Window`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[-10,5,0]`
 - Under [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
  - Set Velocity  to `[10,0,0]`


 #  What is the TimeSpace?


The [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown) component allows for developer control over time in the space it is attached to. Time in that space can be slowed or even stopped. Let's see what the demo looks like right now to get a frame of reference.

  - [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![control](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94788.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

The ball falls, bounces, and rolls at a normal pace for the values it was initialized with.


 ##  TimeScale


A common dramatic effect is to slow down time during some in-game event. Slow motion effects are typically implemented via the [TimeScale](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown#timescale-zero-engine-do) property, which is a scalar for the rate at which time passes. There are also some times where running your project at a slower speed will allow you to debug issues more easily. Let's take a look at how to change TimeScale  using the UI.

(NOTE)**Space Selection**:
 The [Space](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/space.markdown) can be selected via the `Select` menu, by clicking in the viewport and then pressing `Shift + S`, by pressing `Ctrl + Shift + S` with any window in focus, or by using the [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#selectspace) command.
 ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94805.png)

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#selectspace)
- In the `Properties Window`
 - Under [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown)
  - Set TimeScale  to `0.5`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![halfspeed](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94807.gif)


*Demo running half speed with `0.5` TimeScale*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

Now we can see that the time scale directly affects the rate of time without affecting the framerate.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#selectspace)
- In the `Properties Window`
 - Under [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown)
  - Set TimeScale  to `1.0`


 ##  Adjusting TimeScale In Script


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `TimeControl`
- Update the `TimeControl` script to the following:

```lang=csharp, name="TimeControl"
class TimeControl : ZilchComponent
{
  [Property]
  var IncreaseRateKey : Keys = Keys.Up;
  
  [Property]
  var DecreaseRateKey : Keys = Keys.Down;
  
  [Property]
  var TimeScaleRateOfChange : Real = 0.1;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    if(Zero.Keyboard.KeyIsPressed(this.IncreaseRateKey))
      this.ScaleTime(this.TimeScaleRateOfChange);
      
    if(Zero.Keyboard.KeyIsPressed(this.DecreaseRateKey))
      this.ScaleTime(-this.TimeScaleRateOfChange);
  }
  
  function ScaleTime(rateChange : Real)
  {
    var newTimeScale = this.Space.TimeSpace.TimeScale + rateChange;
    this.Space.TimeSpace.TimeScale = Math.Clamp(newTimeScale, 0.0, 2.0);
    Console.WriteLine("TimeScale: `this.Space.TimeSpace.TimeScale`");
  }
}
```

- [Select](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `TimeControl`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Console](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#console)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Adjust the time scale using the `up` and `down` keys



![controlled](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94790.gif)


*TimeScale  being adjusted up and down*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

Above we can see the demo progressing slower and then faster as the [TimeScale](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown#timescale-zero-engine-do) is adjusted using the keyboard.


 #  Pausing


- Add the following property to the `TimeControl` script:
```name=PauseKey Property, lang=csharp
  [Property]
  var PauseKey : Keys = Keys.Space;
```

- Add the following function to the `TimeControl` script:
```name=TogglePause, lang=csharp
  function TogglePause()
  {
    if(this.Space.TimeSpace.Paused)
    {
      Console.WriteLine("Game was paused, unpausing now");
      this.Space.TimeSpace.Paused = false;
    }
    else
    {
      Console.WriteLine("Game was not paused, pausing now");
      this.Space.TimeSpace.Paused = true;
    }
  }
```
- Add the following block to the end of the `OnLogicUpdate` function in the `TimeControl` script:
```name=OnLogicUpdate Extension,lang=csharp
    if(Zero.Keyboard.KeyIsPressed(this.PauseKey))
      this.TogglePause();
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press `Space` to pause the game and then press `Space` again to attempt to unpause the game



![stopped](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94809.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

You probably noticed that the game will not unpause. This is because when the [TimeSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown) is paused, [Keyboard](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/keyboard.markdown), listening for the [KeyDown](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#keydown) event, or to poll the keyboard input on [FrameUpdate](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#frameupdate).

- Update the `Initialize` function in `TimeControl` to the following:
```name=Initialize, lang=csharp
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(Zero.Keyboard, Events.KeyDown, this.OnKeyDown);
  }
```

- Replace the `OnLogicUpdate` function in `TimeControl` with the following:
```name=Initialize, lang=csharp
  function OnKeyDown(event : KeyboardEvent)
  {
    if(event.Key == this.IncreaseRateKey)
      this.ScaleTime(this.TimeScaleRateOfChange);
      
    if(event.Key == this.DecreaseRateKey)
      this.ScaleTime(-this.TimeScaleRateOfChange);
    
    if(event.Key == this.PauseKey)
      this.TogglePause();
  }
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press `Space` to pause the game and then press `Space` again to attempt to unpause the game



![pausing](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94811.gif)


*Pausing with and unpausing in reaction to the [KeyDown](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#keydown) event*


Now we can see the game being paused and unpaused successfully.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)


 #  Related Materials
 ##  Manual
- [LauncherNewProject](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/LauncherNewProject.markdown)
- [commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [selectobject](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)
- [addremovecomponent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
- [resourceadding](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 ##  Reference
 ###  Commands
- [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- [ CreateSphere](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsphere)
- [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#selectspace)
- [ Console](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#console)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 ###  Classes
- [transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
- [timespace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown)
- [rigidbody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
- [boxcollider](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/boxcollider.markdown)
- [keyboard](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/keyboard.markdown)

 ###  Events
- [ LogicUpdate](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#logicupdate)
- [ FrameUpdate](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#frameupdate)
- [ KeyDown](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#keydown)

 ##  Development Tasks
- {T1178} 

 