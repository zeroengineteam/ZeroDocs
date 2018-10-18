This lesson covers how to create archetypes from a script at game runtime.


 # Learning Objectives
 - Creating archetypes from a script
 - Modifing dynamically created objects

 # Level Setup
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `MovementLogic`
- In the `MovementLogic` script
 - Replace the script's contents with the following:

```lang=csharp, name="MovementLogic"
class MovementLogic : ZilchComponent
{
  var Speed : Real = 5.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var dir : Real3 = Real3(0,0,0);
    
    if(Zero.Keyboard.KeyIsDown(Keys.A))
    {
      dir -= Real3.XAxis;
    }
    
    if(Zero.Keyboard.KeyIsDown(Keys.D))
    {
      dir += Real3.XAxis;
    }
    
    this.Owner.RigidBody.Velocity = dir * this.Speed;
  }
}
```

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - [ Remove Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [GravityEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)
 - [ Remove Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [DragEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/drageffect.markdown)

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object 
- In the `Properties Window`
 - Rename Sprite object  to `Player`
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `MovementLogic`

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Play the Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/runthegame.markdown)
 -  Press key `A` and `D`



![Movement](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90547.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Stop Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/StopGame.markdown)

 # Archetype Creation

Before we can spawn objects from script, we need to create the archetype from which the instances (objects) will be created.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename it to `Bullet`
 - Under [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
  - Set the SpriteSource texture to `Cricle`
  - Set the VertexColor  to `Red [R:255, G:0, B:0, A:1.00]`
 - Under [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
  - Set Scale  to `[0.5, 0.5, 0.5]`
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
 - Set `name=Archetype, icon=pencil-square-o` to `BulletArchetype` and click the UploadToArchetype button button.



![BulletArchetype](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90549.gif)


 - Delete the Bullet object

 # Spawning Archetypes

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `ShootingLogic`
- In the `ShootingLogic`
 - Replace the script's contents with the following:

```lang=csharp, name="ShootingLogic"
class ShootingLogic : ZilchComponent
{
  
  var BulletSpeed : Real = 10.0;
  
  var ShotCooldown : Real = 0.4;
  
  var Timer : Real = 0.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    this.Timer += event.Dt;
    
    if(Zero.Keyboard.KeyIsDown(Keys.Space) && this.Timer > this.ShotCooldown)
    {
      var bullet = this.Space.CreateAtPosition(Archetype.BulletArchetype, this.Owner.Transform.Translation);
      bullet.RigidBody.Velocity = Real3(0, this.BulletSpeed, 0);
      this.Timer = 0.0;
    }
  }
}
```

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Player object
- In the `Properties Window`
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `ShootingLogic` component
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Play the Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/runthegame.markdown)
 - Press key `A` and `D` keys to move
 - Press key `Space` key to shoot



![Shooting](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90561.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Stop the Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/StopGame.markdown)

Let's take a closer look inside the `ShootingLogic`'s LogicUpdate function:

> `this.Timer += event.Dt;` 
> Increases our `Timer` variable by time elapsed since last frame.

> `if(Zero.Keyboard.KeyIsDown(Keys.Space) && this.Timer > this.ShotCooldown)` 
> Checks whether `Space` is pressed and if `Timer` is greater than `ShotCooldown`

> `var bullet = this.Space.CreateAtPosition(Archetype.BulletArchetype, this.Owner.Transform.Translation);`
> Creates an Instance of the `BulletArchetype` at the owner's position and stores it in a local variable


> `bullet.RigidBody.Velocity = Real3(0, this.BulletSpeed, 0);`
> Uses the local variable to access the newly created object and sets its velecity

> `this.Timer = 0.0;`
> Resets the `Timer`


 # Related Materials

 ## Manual
- [ COGs](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown)
- [ Archetypes](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/archetypes.markdown)
- [ Play the Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/runthegame.markdown)
- [ Stop the Game](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/StopGame.markdown)
- [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 ## Reference
 ### Classes
- [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Transform.markdown)
- [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Sprite.markdown)
- [Cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Cog.markdown)
- [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
- [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
- [GravityEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)
- [DragEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/drageffect.markdown)

 ### Commands
- [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)

 ## Task
- T888 
  
  
  
  
  
  
  

 