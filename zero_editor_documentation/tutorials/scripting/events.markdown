Events are the main way that [Cogs](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/gameobjects.markdown) and [components](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/basiccomponents.markdown) communicate to each other in the Zero Engine. Often a component has information it needs to communicate to other components, one of the most flexible ways to do so is to package the information into an Event and then dispatch the event on an object. Then, any components that need the information can “listen” for the event to be dispatched, accessing that information in a special callback function.

There are two types of events in the Zero Engine: built-in events and custom events. This lesson will cover built-in events while the next lesson will go over custom events.


 #  Learning Objectives


- The [LogicUpdate](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#logicupdate) Event
- [ CollisionEvents](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisionevent.markdown)
- Destruction events


 #  Level Setup


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - [ Remove Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) :  [gravityeffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)
 - [ Remove Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) :  [drageffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/drageffect.markdown)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Player`
 - Under [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:0, G:170, B:255, A:1.00]`
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/BoxCollider.markdown)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `PlayerMovement`

To get our player moving around we'll be using [LogicUpdate](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#logicupdate), an [updateevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/updateevent.markdown) that is dispatched on the space object every frame. Movement can be easily added by polling which [Keys](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#keys) are currently being pressed, if any, and updating the velocity of the object based on the keypress.

- Update the `PlayerMovement` script to the following:

```lang=csharp, name=PlayerMovement
class PlayerMovement : ZilchComponent
{
  [Dependency] var RigidBody : RigidBody;

  [Property]
  var MoveRight : Keys = Keys.D;
  
  [Property]
  var MoveLeft : Keys = Keys.A;
  
  [Property]
  var MoveUp : Keys = Keys.W;
  
  [Property]
  var MoveDown : Keys = Keys.S;
  
  [Property]
  var MoveSpeed : Real = 5;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    var movement : Real3 = Real3();
    
    if(Zero.Keyboard.KeyIsDown(this.MoveRight))
      movement += Real3.XAxis;
      
    if(Zero.Keyboard.KeyIsDown(this.MoveLeft))
      movement -= Real3.XAxis;
      
    if(Zero.Keyboard.KeyIsDown(this.MoveDown))
      movement -= Real3.YAxis;
      
    if(Zero.Keyboard.KeyIsDown(this.MoveUp))
      movement += Real3.YAxis;
      
    this.RigidBody.Velocity = movement * this.MoveSpeed;
  }
}
```
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `PlayerMovement`
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![KeyPolling](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94456.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

`LogicUpdate` is the event and `this.OnLogicUpdate` is the event callback function. A callback function is a function passed as an argument into another function, with the expectation that it will be called in response to something.  An event callback function (in this case, this.OnLogicUpdate) is the function that is called every time a component (in this case, PlayerMovement) that is connected to some event (in this case, LogicUpdate) hears that the event has occurred (which is every frame in this instance). As `OnLogicUpdate` is called every frame, seamless movement can be achieved by updating the movement vector of the Cog within that function.

 ## Event Connections

Connecting to an event involves both calling the [Zero.Connect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/zero.markdown#connect-void-key-static) function and creating the appropriate callback function. Let's look at the call to the Connect function first, parameter by parameter:

```lang=csharp, name=Example Event Connect Function Call
Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
```

| Example Value | Parameter Type | Description 
|---|---|---
| `this.Space` | [ Object](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/object.markdown) | The object onto which the event will be dispatched. 
| `Events.LogicUpdate` | [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown) | The name of the event.
| `this.OnLogicUpdate` | [ Delegate](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/delegates.markdown) | The callback function for the event.

The callback function must take a parameter whose type matches the type of the event that you are connecting to. Now let's take a look at the callback function:

```lang=csharp, name=LogicUpdate callback function
function OnLogicUpdate(event : UpdateEvent)
```

| Example Value | Parameter Type | Description
|---|---|---
| `event` | [updateevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/updateevent.markdown) | An event whose type matches the type included with the declaration of the event name.

Note that LogicUpdate is already declared to use an UpdateEvent; however, we can also declare our own events in Zilch. When we do declare our own, we then specify the the types of events they will use (whether it's a pre-existing event or a custom event we make ourselves, as will be seen in the next lesson). As we will see, there are many types of events that may be connected to, starting with built-in events that are engine-constructed. 

 ## Built-In Events

Built-in events are provided for you ready to connect. They are always dispatched by the engine under a consistent and specific context. Examples of built-in events include [mouseevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/mouseevent.markdown), [keyboardevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/keyboardevent.markdown), and [soundevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundevent.markdown). We've already seen the [LogicUpdate](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#logicupdate) event; now let's check out how some other built-in events can be used.

 ### Collision Events

There are three main [Collision events](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisionevent.markdown): [CollisionStarted](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionstarted), [CollisionPersisted](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionpersisted), and [CollisionEnded](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionended). When an object with a collider comes into contact with another collider, a CollisionStarted event is created by the physics engine and is dispatched that frame on both objects involved in the collision. In the following frames, if the object's colliders are still in contact, the CollisionPersisted event is dispatched on the objects. The first frame the colliders are no longer in contact the CollisionEnded event is dispatched on both objects. To demonstrate a Collision event, let's make a simple enemy sprite:

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Enemy`
 - Under [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
   - Set Translation  to `[4, 0, 0]`
 - Under [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R: 255, G: 0, B: 0, A;1.00]`
  - Set SpriteSource enum to `Circle`
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/BoxCollider.markdown)

Now we need to create another component that will destroy the player cog in response to the collision event.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `DestroyOnCollide`
- Update the `DestroyOnCollide` script to the following:

```lang=csharp, name=DestroyOnCollide
class DestroyOnCollide : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Owner, Events.CollisionStarted, this.OnCollisionStarted);
  }

  function OnCollisionStarted(event : CollisionEvent)
  {
    this.Owner.Destroy();
  }
}
```
- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Player object
 - [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `DestroyOnCollide`
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![CircleAndSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94458.gif) *Player cog being destroyed upon collision with an enemy cog.*


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 ### Destruction Events

Another useful built-in event is the [CogDestroy](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#cogdestroy) event which is dispatched on a cog the frame its Destroy function is called. These can be used to add effects or to update the UI when the player or enemies have been destroyed. Let's create a component that will create a particle effect on the destruction of our player.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `SpawnObjectOnDestroy`
- Update the `SpawnObjectOnDestroy` script to the following:

```lang=csharp, name=SpawnObjectOnDestroy
class SpawnObjectOnDestroy : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var ArchetypeToSpawn : Archetype = Archetype.SpriteParticles;

  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Owner, Events.CogDestroy, this.OnCogDestroy);
  }
 
  function OnCogDestroy(event : ObjectEvent)
  {
    var object = this.Space.CreateAtPosition(this.ArchetypeToSpawn, this.Transform.Translation);
    var selectionIcon = object.SelectionIcon;
    if (selectionIcon != null)
      selectionIcon.Visible = false;
  }
}
```
- [Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `SpawnObjectOnDestroy`
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![DestructionEffect](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94459.gif)


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

Now we can see the particle system object being created in our event response function. In the [ next tutorial](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/scripting/events_ii.markdown), we will cover custom events, which are events you define and dispatch.


 #  Related Materials
 ##  Tutorial
- [gameobjects](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/gameobjects.markdown)
- [basiccomponents](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/architecture/basiccomponents.markdown)
- [events_ii](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/scripting/events_ii.markdown)

 ##  Manual
- [commands](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [selectobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)
- [resourceadding](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [addremovecomponent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)

 ##  Reference
 ###  Class
- [collisionevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collisionevent.markdown)
- [gravityeffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gravityeffect.markdown)
- [drageffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/drageffect.markdown)
- [sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
- [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
- [BoxCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/BoxCollider.markdown)
- [updateevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/updateevent.markdown)
- [zero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/zero.markdown)
- [mouseevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/mouseevent.markdown)
- [keyboardevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/keyboardevent.markdown)
- [soundevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundevent.markdown)
- [objectevent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectevent.markdown)

 ###  Command
- [ NewProject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
- [ CreateSprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 ###  Event
- [ LogicUpdate](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#logicupdate)
- [ CollisionStarted](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionstarted)
- [ CollisionPersisted](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionpersisted)
- [ CollisionEnded](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#collisionended)
- [ CogDestroy](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/event_reference.markdown#cogdestroy)

 ###  Enums
- [ Keys](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#keys)

 ###  Zilch Base Types
- [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

 ##  Development Task
- T781 
  
  
  
  
  
  
  

 