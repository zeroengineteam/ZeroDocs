This page outlines the steps need to create a basic version of the classic game Asteroids. You should make sure you understand the content of the #basic_tutorials tagged with #beginner_iii before beginning this project.

NOTE: Like other project pages this tutorial does not cover every tiny step the user must complete and instead summarizes. This requires the reader to understand basic concepts from preceeding tutorials to complete the project.

 # Learning Objectives

- Reaffirm the learning objectives of #beginner_iii tutorials.

 # Level Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
- [Remove ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) the [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) from the LevelSettings object.
- [Remove ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) the [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown) from the LevelSettings object.

 # The Player
 ## Player Archetype
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
 - Rename the new sprite to `Player`
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) to the Player object
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) [Orientation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown) to the Player object
 - Set [Orientation.DefaultOrienationBases](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown#defaultorientationbases) to [ForwardZUpY](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#orientationbases)
- Upload the Player object to a new archetype called `Player`

 ## Player Movement
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- Create a ZilchScript resource using the Component template template and name it `PlayerMovement`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `PlayerMovement` to the Player object
- Upload the Player object to a new archetype called `Player`

 ### Properties
- Define properties of type [Keys](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#keys) in `PlayerMovement` for the forward, backward, left, right, and shoot keys for the player
- Define properties of type [Real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown) called `Speed` and `RotationSpeed`

 ### Moving
- Connect to [LogicUpdate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#logicupdate) in the `PlayerMovement` component.
- In `PlayerMovement` in `OnLogicUpdate`
 - Declare a local `movement` variable
 - Check if the `Forward` and `Backward` input keys defined above are down using [Zero.Keyboard.KeyIsDown()](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisdown-zero-engine-do)
 - If the `Forward` is down add [Orientation.WorldForward](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown#worldforward-zero-engine) to `movement`
 - If the `Backward` is down subtract [Orientation.WorldForward](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown#worldforward-zero-engine) to `movement`
 - [Normalize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/math.markdown#normalize-zero-engine-do) `movement`
 - Set [RigidBody.Velocity](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown#velocity-zero-engine-doc) to `movement * this.Speed`

 ### Rotating
- In `PlayerMovement` in `OnLogicUpdate`
 - Declare a local `rotation` variable
- Check if the `Left` and `Right` input keys defined above are down using [Zero.Keyboard.KeyIsDown()](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisdown-zero-engine-do)
 - If the `Left` is down add [Orientation.WorldUp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown#worldup-zero-engine-docu) to `rotation`
 - If the `Right` is down subtract [Orientation.WorldUp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown#worldup-zero-engine-docu) to `rotation`
- Declare a local variable `rotationSpeedRadians` and initialize it to `RotationSpeed` converted [to radians](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/math.markdown#toradians-zero-engine-do).
- Use [Transform.RotateWorld()](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotateworld-void) to rotate the object by `rotation * rotationSpeedRadians * event.Dt`

 ## Player Shooting
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- Add a ZilchScript resource using the Component template template and name it `ObjectSpawner`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `ObjectSpawner` to the Player object
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- Add a ZilchScript resource using the Component template template and name it `CreateOnInput`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `CreateOnInput` to the Player object
- Upload the Player object to a new archetype called `Player`

 ### Properties
- In `ObjectSpawner`
 - Define a property of type [Archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/archetype.markdown) named `ArchetypeToSpawn`
 - Define a property of type [Real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown) named `InitialVelocity`
 - Define a property of type [Boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown) named `UseRandomDirection` (defaulting to `false`)

- In `CreateOnInput`
 - Define a property of type [Keys](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#keys) in `ObjectSpawner` named `SpawnKey`

 ### Spawning Projectiles
- In the `ObjectSpawner` component
 - Create a new function named `SpawnObject()`
 - In `SpawnObject()`
  - [Create](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/space.markdown#createatposition-zero-en) a `ArchetypeToSpawn` object at the [position](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#worldtranslation-zero-en) of the Player object
  - If `ObjectSpawner.UseRandomDirection` is true then get a normalized random direction, or if `UseRandomDirection` is false use `Orientation.WorldForward` for the direction of the object's inital velocity.
  - Set the initial velocity of the object.


- In the `CreateOnInput` component.
 - Connect to [LogicUpdate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#logicupdate)
 - In `OnLogicUpdate`
  - Check if `SpawnKey` is down using [Zero.Keyboard.KeyIsDown()](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisdown-zero-engine-do)
  - If `SpawnKey` is down then call `ObjectSpawner.SpawnObject()`

 - Set the [velocity](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown#velocity-zero-engine-doc) of the newly created Projectile object to `this.InitialVelocity * this.Owner.Orientation.WorldForward`


 # The Projectile
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- Create a ZilchScript resource using the Component template template and name it `DestroyOnCollision`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `DestroyOnCollision` to the Projectile object
- Under the `Sprite` component change the `VertexColor`
- Upload the Projectile object to a new archetype called `Projectile`

 ## DestroyOnCollision
 ### Properties
- In `DestroyOnCollision`
 - Define a property of type [Boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown) named `DestroyOwner` (defaulting to `false`)
 - Define a property of type [Boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown) named `DestroyOther` (defaulting to `false`)

 ### Destroying On Collision
- In `DestroyOnCollision`
 - Connect to the `CollisionStarted` event
 - In `OnCollisionStarted`
  - If `DestroyOther` is true call `event.OtherObject.Destroy()`
  - If `DestroyOwner` is true call `this.Owner.Destroy()`

- Play the game
 - At this point the ship should be able to move, rotate, and shoot.

 # Astroids
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
 - Rename the new sprite to `Asteroid`
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) to the Asteroid object
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown) to the Asteroid object
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `DestroyOnCollision` to the Asteroid object
- Upload the `Asteroid` archetype

 ## Spawning Asteroids
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
 - Rename the new sprite to `AsteroidSpawner`
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) [Orientation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/orientation.markdown) to the AsteroidSpawner object
- [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `ObjectSpawner` to the AsteroidSpawner object

 ### CreateOnInterval Component
- Add a ZilchScript resource using the Component template template and name it `CreateOnInterval`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `CreateOnInterval` to the AsteroidSpawner object
- Move the AsteroidSpawner object outside the viewport so the GameCamera object can not see it
- Upload the AsteroidSpawner object to a new archetype called `AsteroidSpawner`

 ### Properties
- In `CreateOnInterval`
 - Define a property of type [Real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown) in `CreateOnInterval` named `SpawnRate`
 - Define a property of type [Boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown) in `CreateOnInterval` named `StartOnInit` defaulting to `true`
 - Define a non-property member variable of type [ActionsSet](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/actionset.markdown) in `CreateOnInterval` named `SpawnSequence`

 ### Interval Spawning
- In `CreateOnInterval`
 - Declare a function named `StartSpawnSequence`
 - In `StartSpawnSequence`
  - Construct a new ActionSequence using `this.Owner.Actions` and assign it to the member variable `SpawnSequence`
   - Construct a `Delay` action using `SpawnSequence` and `SpawnRate`
   - Construct a `Call` action using `SpawnSequence` and `ObjectSpawner.SpawnObject`
   - Construct a `Call` action using `SpawnSequence` and `StartSpawnSequence`
 - In the `Initialize` function
  - If `StartOnInit` is `true`
   - Call `StartSpawnSequence`

 # The ScreenWrap Component
- Add a ZilchScript resource using the Component template template and name it `ScreenWrap`
 - [Add component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) `ScreenWrap` to the Asteroid resource and Player resource archetypes

 ## ScreenWrapping

- The `ScreenWrap` component should look like this

```name=ScreenWrap, lang=csharp
class ScreenWrap : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var Camera : CogPath = CogPath();
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    //Get the viewport component
    var viewport = this.Camera.Cog.CameraViewport;
    
    //prevent dividing by zero when the viewport resolution is (0,0) on game close
    if(Math.LengthSq(viewport.ViewportResolution) == 0.0)
      return;
      
    //get the normalized viewport
    var worldPos = this.Transform.WorldTranslation;
    var screenPos = viewport.WorldToScreen(worldPos);
    var viewportPos = viewport.ScreenToViewport(screenPos);
    var normalizedViewportPos = viewportPos / viewport.ViewportResolution;
    
    //screen wrap in normalized viewport space
    if(normalizedViewportPos.X > 1.0)
      normalizedViewportPos.X = 0.0;
    else if(normalizedViewportPos.X < 0.0)
      normalizedViewportPos.X = 1.0;
    
    if(normalizedViewportPos.Y > 1.0)
      normalizedViewportPos.Y = 0.0;
    else if(normalizedViewportPos.Y < 0.0)
      normalizedViewportPos.Y = 1.0;
    
    //convert the wrapped viewport position to world space
    viewportPos = normalizedViewportPos * viewport.ViewportResolution;
    screenPos = viewport.ViewportToScreen(viewportPos);
    worldPos = viewport.ScreenToWorldZPlane(screenPos, worldPos.Z);
    
    //set the object's position
    this.Transform.WorldTranslation = worldPos;
  }
}
```

- Drag and drop an instance of the Asteroid Asteroid resource and Player resource in the level
- Under ObjectSpawner
 - Set the `Camera` CogPath property to reference the Gamecamera object



![Asteroids](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94409.zip)


At this point you should have a small ship navigating the screen, shooting, screenwrapping, and destroying asteroids. 

 