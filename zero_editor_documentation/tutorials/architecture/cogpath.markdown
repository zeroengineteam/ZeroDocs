[CogPaths](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cogpath.markdown) provide the best way to get a reference to any [Cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown) before running the game. Often you will find situations where a component needs to be aware of a paticular object when the game starts. While CogPaths are not limited to only working at load time this is where they are most useful.


 #  Learning Objectives


- CogPath properties
- Accessing components on other objects


 #  Level Setup


First we will make the ground and player objects.
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
 - [Remove component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [gravityeffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)

- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Add resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `PlayerController`
- Update `PlayerController` script to the following code block:

```name=PlayerController, lang=csharp
class PlayerController : ZilchComponent
{
  [Property]
  var Speed : Real = 5.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var direction = Real3();
    
    if(Zero.Keyboard.KeyIsDown(Keys.Right))
      direction.X += 1.0;
    
    if(Zero.Keyboard.KeyIsDown(Keys.Left))
      direction.X += -1.0;
    
    if(Zero.Keyboard.KeyIsDown(Keys.Up))
      direction.Y += 1.0;
    
    if(Zero.Keyboard.KeyIsDown(Keys.Down))
      direction.Y += -1.0;
    
    this.Owner.RigidBody.Velocity = direction * this.Speed;
  }
}
```
- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `name=Properties Window, icon=window-restore`
 - Rename Sprite object to `Player`
 - [Add component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
 - [Add component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [boxcollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown)
 - [Add component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `PlayerController`
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
 - Press `Left`, `Right`, `Up` and `Down`



![simpleinput](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90208.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 # The Follower

- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Add resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `FollowerController`
- Update `FollowerController` script to the following code block:

```name=FollowerController, lang=csharp
class FollowerController : ZilchComponent
{
  [Property]
  var PlayerCogPath : CogPath = CogPath();
  
  var Speed : Real = 5.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var targetPos = this.PlayerCogPath.Cog.Transform.Translation;
    var myPos = this.Owner.Transform.Translation;
    var direction = Math.Normalize(targetPos - myPos);
    this.Owner.RigidBody.Velocity = direction * this.Speed;
  }
}
```

In the script above the position of the player and the position of the follower are used to calculate a unit vector which defines the 3D direction from the follower to the player. By multiplying it with `this.Speed` a velocity is defined which can be applyed to move the follower object.

(NOTE)**Initializing a CogPath Property**: Notice that a CogPath constructor was acutally called in the definition of the `PlayerCogPath` property. CogPath's are one of the few types that require a manual construction where as Zilch value types can have their initial value infered: i.e. `var MemberVariable : Real;` in this case `MemberVariable` will have the default type value of `0`.

- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `name=Properties Window, icon=window-restore`
 - Set `name=Name, icon=pencil-square-o` to: `Follower`
 - [Add component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [boxcollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown)
 - [Add component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `FollowerController`
 - Under [sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
   - Set `name=VertexColor, icon=eyedropped` to: `[0,0,1,1]`
 - Under [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
   - Set `name=Translation, icon=pencil-square-o` to: `[-5,0,0]`

 ##  Setting a CogPath
 - Under `FollowController`

  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90210.png)

This is the CogPath Property GUI. To select which object the CogPath points add you simple click on the Crosshairs and drag them to the target object.



![SetCogPath](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90218.gif)


  - Set `name=PlayerCogPath, icon=pencil-square-o` to reference the Player object

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
 - Press `Left`, `Right`, `Up` and `Down`



![Follower](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90220.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 # CogPaths and Hierarchies

- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `name=Properties Window, icon=window-restore`
 - Set `name=Name, icon=pencil-square-o` to: `Child`
 - Under [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
   - Set `name=Translation, icon=pencil-square-o` to: `[2,0,0]`
   - Set `name=Scale, icon=pencil-square-o` to: `[0.5,0.5,0.5]`
- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Child object
 - Drag and drop it on the Player object object

  ![ChildToPlayer](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90222.gif)

- [Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `name=Properties Window, icon=window-restore`
 - Set `name=Name, icon=pencil-square-o` to: `Parent`
 - Under [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
   - Set `name=Translation, icon=pencil-square-o` to: `[0,2,0]`
   - Set `name=Scale, icon=pencil-square-o` to: `[0.5,0.5,0.5]`
- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Player object
 - Drag and drop it on the Parent object object

  ![PlayerToParent](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90364.gif)

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
 - Press `Left`, `Right`, `Up` and `Down`

 ![TestChildPlayer](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90230.gif)

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

It can be seen that the Player object moves independently of its parent object do to it having its own RigidBody. However, you may be wondering why the follower no longer goes to the same position as the Player object. If you remember from [Hierarchies I](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/hierarchies.markdown), Player object is now a child object meaning its `name=Translation, icon=pencil-square-o` is measured relative to it's paren object. Since the `FollowerController` was not changed to use the explicit `name=WorldTranslation, icon=pencil-square-o` of the Player object, the Follower object moves to the same offset of the Player object as it starts with its Parent object.

- [Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) the Follower object object
 - Under `FollowerController`
  - Examine the text of the `name=PlayerCogPath, icon=pencil-square-o` property

Notice that the CogPath text has not changed despite the fact that the player hierarchy order has changed.

  - Set `name=PlayerCogPath, icon=pencil-square-o` to reference the Player object

 ![ResetCogPath](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90232.gif)

Notice that the text of `name=PlayerCogPath, icon=pencil-square-o` changes from `:/Player` to the correct path of `:/Parent/Player`. You may be wondering why it worked when the project was run last. When CogPath properties are set they capture a reference at that moment as opposed to waiting for the level to be loaded into the game. When the path to an object targeted by a CogPath changes it does not lose that direct reference to the object, but instead the Path becomes inaccurate. You should not depend on this behavior and you should always reset your CogPath properties to have the correct path when possible. If you wish to learn more about the complex behaviors of the direct cog reference visit the [CogPaths Manual Page](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/cogpathsmanual.markdown).


- In the `FollowerController` script update `OnLogicUpdate` to this code block

```name=FollowerController OnLogicUpdate, lang=csharp
function OnLogicUpdate(event : UpdateEvent)
{
  var targetPos = this.PlayerCogPath.Cog.Transform.WorldTranslation;
  var myPos = this.Owner.Transform.Translation;
  var direction = Math.Normalize(targetPos - myPos);
  this.Owner.RigidBody.Velocity = direction * this.Speed;
}
```

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

 - Press `Left`, `Right`, `Up` and `Down`

 ![FollowWorldTrans](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90366.gif)

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

Now the Follower object follows the Player object `name=WorldTranslation, icon=pencil-square-o` correctly.

 # Related Materials
 # Manual
- [CogPaths](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/cogpathsmanual.markdown)
- [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 # Tutorials
- [hierarchies](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/hierarchies.markdown)

 # Reference
 ### Classes
- [CogPaths](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cogpath.markdown)
- [gravityeffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)
- [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
- [boxcollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown)
- [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)

 ### Commands
- [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)
- [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)


 # Tasks
- T864
 
  
  
  
  
  
  
  

 