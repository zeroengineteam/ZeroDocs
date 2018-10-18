This lesson covers how to manipulate object hierarchies in Zilch.


 #  Learning Objectives


- Parenting / unparenting objects at runtime
- Accessing objects through the hierarchy in code


 #  Level Setup


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Add Resource](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#add)
 - Create a ZilchScript resource using the Component template template and name it `SquareLogic`
- [Select](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Square`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `SquareLogic`
- Update the `SquareLogic` script to the following:
```lang=csharp, name="SquareLogic"
class SquareLogic : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var RotateSpeed : Real = 5.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var vel = this.RotateSpeed * event.Dt;
    this.Transform.RotateAnglesWorld(Real3(0.0, 0.0, vel));
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![HierarchiesSetup](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96155.gif)


*The Square object rotates*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)


 #  Parenting at Runtime


Let's create an archetype that can be used later to spawn child cogs at runtime.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Circle`
 - Under [Sprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sprite.markdown)
  - Set SpriteSource enum to `Circle`
 - Set Archetype  to `CircleArchetype`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Delete](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#delete)

Now let's modify the `SquareLogic` component to spawn circles and parent them to the Square object

- Update the `SquareLogic` script to the following:

```lang=csharp, name=Square Logic
class SquareLogic : ZilchComponent
{
  [Dependency] var Transform : Transform;

  [Property]
  var RotateSpeed : Real = 5.0;
  
  [Property]
  var ArchetypeToSpawn : Archetype = Archetype.CircleArchetype;
  
  [Property]
  var SpawnLocation : Real3 = Real3(0.0, 2.0, 0.0);
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var vel = this.RotateSpeed * event.Dt;
    this.Transform.RotateAnglesWorld(Real3(0.0, 0.0, vel));
    
    if(Zero.Keyboard.KeyIsPressed(Keys.Space))
    {
      var obj = this.Space.CreateAtPosition(this.ArchetypeToSpawn, this.SpawnLocation);
      obj.AttachTo(this.Owner);
    }
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press key the `Space` key



![HierarchiesAttach](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96165.gif)


*The `Space` bar spawns child Circle object objects*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

Notice that the Circle object is attached to the Square object object as soon as it is created. That is done through invoking the [AttachTo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown#attachto-zero-engine-doc) function on [ Cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown), which takes a designated parent cog as its only parameter.

Similarly, you can call the [Detach](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown#detach-void) function to unparent any object from its hierarchy:

- Add the following to the end of `OnLogicUpdate` function in the `SquareLogic` component:

```lang=csharp, name=Detaching
if(Zero.Keyboard.KeyIsPressed(Keys.D))
{
   this.Owner.Children.Current.Detach();
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press key the `Space` key a few times
 - Press key the `D` key a few times



![HierarchiesDettach](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96252.gif)


*The `D` key detaches the child Circle object objects*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

NOTE: Zero also sends the [ Attached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#attached) and [ Detached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#detached) events to cogs when the respective operation is performed on them. Additionally, you can connect to the [ ChildAttached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#childattached) and [ ChildDetached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#childdetached) events on a parent objecct if you want to perform some logic upon acquiring or losing a child.


 #  Traversing Hierarchies at Runtime


Within a script, you can easily access a cog's parent:

- Add the following to the `SquareLogic` class:

```lang=csharp, name=Growth Property
[Property]
var Growth : Real = 1.1;
```

- In the `SquareLogic` class
 - In the `OnLogicUpdate` function
  - Below the line, `obj.AttachTo(this.Owner);`
   - Add the following code:

```lang=csharp, name=Accessing Parent
obj.Parent.Transform.Scale *= this.Growth;
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press key the `Space` key



![HierarchiesParentAccess](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96244.gif)


*The `Space` bar now also grows the parent Square object object*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

You can also get a range containing all immediate children. Let's implement an addition to our previous script.

- Add the following to `OnLogicUpdate` function in the `SquareLogic` component:

```lang=csharp, name=Accessing Children
    if(Zero.Keyboard.KeyIsPressed(Keys.Enter))
    {
      foreach(var child in this.Owner.Children)
      {
        child.Sprite.VertexColor = Colors.Red;
      }
    }
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - Press key the `Space` key a few times
 - Press key the `Enter` key



![HierarchiesChildren](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96250.gif)


*The `Enter` key now turns the child Circle object objects red*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)


 #  Related Materials
 ##  Tutorials
- [hierarchies](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/architecture/hierarchies.markdown)

 ##  Manual
- [gameobjectsconcept](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown)
- [archetype_basics](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/archetypes/archetype_basics.markdown)

 ##  Reference
 ###  Classes
- [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)
- [transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/transform.markdown)
- [sprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sprite.markdown)

 ###  Events
- [ Attached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#attached)
- [ Detached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#detached)
- [ ChildAttached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#childattached)
- [ ChildDetached](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#childdetached)

 ###  Commands
- [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)
- [ Delete](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#delete)

 ##  Development Task
- T1189 

 