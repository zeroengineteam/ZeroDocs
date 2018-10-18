This lesson discusses audio in the Zero Engine.

(NOTE) **You will need speakers, headphones, or some other audio output device for this lesson.**

 #  Learning Objectives

- The [soundemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown) interface
- The [soundspace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown) interface
- [soundinstance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown)

 #  Level Setup
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- Download the following files:


![SFX_Explosion](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/97294.wav)



![BG_Arpeggios](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/97295.ogg)

- Import them into the project by dragging and dropping the files into the `Level Window`
- In the `Group Import Options Window`
 - Set GenerateCue enum to `PerSound`
 - Press the `Import All` button
- In the `Library Window`
 - Under the SoundCue  tag
  - Double-click  the `BG_Arpeggios` SoundCue
- In the `Properties Window`
 - Set PlayMode enum to `Looping`
- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : GameCamera object
- In the `Properties Window`
 - Under [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 0, 3]`
 - Under [ Camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown)
  - Set Size  to `40`

 #  SoundEmitter

There are a few different ways to play sounds in the Zero Engine. One is by using a [ SoundEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown). The SoundEmitter component is used to play [ SoundCues](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundcue.markdown) //positionally//: that is, as if they were to occur in the world with the rest of the game. Using positional audio, it is possible to create, for example, an explosion effect that is louder or softer, and will sound like it occurs to the left or right of the player, depending on where it goes off.

Let's do that now.

 ##  The PlayCue Function

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `KeyboardMovement`
- Update `KeyboardMovement` to the following:

```lang=csharp, name="KeyboardMovement"
class KeyboardMovement : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var Speed : Real = 20.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }
  
  function OnLogicUpdate(event : UpdateEvent)
  {
    var movement = Real3.Zero;
    
    if (Zero.Keyboard.KeyIsDown(Keys.Right))
      movement += Real3.XAxis;
    if (Zero.Keyboard.KeyIsDown(Keys.Left))
      movement -= Real3.XAxis;
    if (Zero.Keyboard.KeyIsDown(Keys.Up))
      movement += Real3.YAxis;
    if (Zero.Keyboard.KeyIsDown(Keys.Down))
      movement -= Real3.YAxis;
    
    movement = Math.Normalize(movement) * this.Speed * event.Dt;
    this.Transform.WorldTranslation += movement;
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Set Name  to `Player`
 - Under [ Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set SpriteSource enum to `Circle`
  - Set VertexColor  to `[R:30, G:150, B:230, A:1.00]`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `KeyboardMovement`

In order for a sound played by a SoundEmitter to be heard, it needs to be picked up by a [ SoundListener](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundlistener.markdown). The GameCamera object object has a SoundListener component. To make the sound effects sound like they're coming from different sides of the player, we can parent the camera to the player so that it automatically follows the player around.

- [ Attach](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/architecture/hierarchies.markdown) GameCamera object to Player object
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `SoundController`
- Update `SoundController` to the following:

```lang=csharp, name="SoundController"
class SoundController : ZilchComponent
{
  [Dependency]
  var SoundEmitter : SoundEmitter;
  
  [Property]
  var ExplosionCue : SoundCue = SoundCue.SFX_Explosion;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }
  
  function OnLogicUpdate(event : UpdateEvent)
  {
    if (Zero.Keyboard.KeyIsPressed(Keys.Space))
      this.SoundEmitter.PlayCue(this.ExplosionCue);
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Set Name  to `Speaker`
 - Under [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 3, 0]`
 - Under [ Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:230, G:60, B:60, A:1.00]`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `SoundEmitter`
 - Under [ SoundEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown)
  - Set Attentuator enum to `DefaultAttenuation`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `SoundController`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96146.png)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- Hold key the `Arrow` keys to move the player around, and press key the `Space` bar to play the explosion sound



![Player movement around speaker](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96141.gif)


If you press `Space`, the speaker plays an explosion sound. If you're on the right side of the speaker, the sound comes from your left, and if you're on the left side, it comes from your right. If you're near the speaker, the explosion sound is louder than if you're far from it.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 ##  The Volume Property

Every sound played by a SoundEmitter is played at the volume level specified by its `Volume` property. Let's play around a bit with that.

- Add the following to the `OnLogicUpdate` function of the `SoundController` class:

```lang=csharp, name="SoundController (continued 1)"
if (Zero.Keyboard.KeyIsDown(Keys.LeftBracket))
{
  this.SoundEmitter.Volume -= event.Dt;
  Console.WriteLine("Current Volume: `this.SoundEmitter.Volume`");
}

if (Zero.Keyboard.KeyIsDown(Keys.RightBracket))
{
  this.SoundEmitter.Volume += event.Dt;
  Console.WriteLine("Current Volume: `this.SoundEmitter.Volume`");
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Console](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#console)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- Press key the `Space` bar to play the explosion sound, and hold key the `[` and `]` keys to decrease and increase the SoundEmitter's volume



![Console printing showing volume changes](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/96161.gif)


*The console shows the changes to the emitter's volume level*


The volume level of the SoundEmitter can now be controlled, in addition to any attenuation that may occur when moving closer to or further from the speaker.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

What if we want to modify the volume of a SoundEmitter gradually over time, but we want it to happen automatically, without having to hold keys on the keyboard? We've already covered [ Actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/actions.markdown): we *could* use an [ Action](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/action.markdown) to interpolate the SoundEmitter's `Volume` property, but as it happens, SoundEmitter has a handy function for just such an occasion.

 ##  The InterpolateVolume Function

- Replace the `OnLogicUpdate` function of the `SoundController` class with the following:

```lang=csharp, name="SoundController (continued 2)"
function OnLogicUpdate(event : UpdateEvent)
{
  if (Zero.Keyboard.KeyIsPressed(Keys.Space))
    this.SoundEmitter.PlayCue(this.ExplosionCue);
  
  if (Zero.Keyboard.KeyIsPressed(Keys.LeftBracket))
    this.SoundEmitter.InterpolateVolume(0, 3);
  
  if (Zero.Keyboard.KeyIsPressed(Keys.RightBracket))
    this.SoundEmitter.InterpolateVolume(1, 3);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- `Repeatedly press` the `Space` bar to play the explosion sound, and press key the `[` and `]` keys to interpolate the SoundEmitter's volume

Now it just takes one press of the `[` and `]` keys to gradually fade the SoundEmitter's volume level down and up, respectively.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

For positional sounds, a SoundEmitter is the way to go, but sometimes audio shouldn't be played positionally. Music, for example, is usually played at a consistent volume level that is independent of the game world, and many sound effects are as well. To make a sound play non-positionally, we'll have to take a look at the [ SoundSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown).

 #  SoundSpace

A [ previous tutorial](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/architecture/spaces.markdown) mentioned the concept of the [ Space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/space.markdown). A space has a few unique components that subdivide its responsibility into different areas. To that end, the [soundspace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown) is "in charge" of any sound that occurs in a space. That is, a SoundListener in one space won't "hear" anything played by a SoundEmitter in another space, because the listener and the emitter are controlled by different SoundSpaces.

The SoundSpace manages all sounds played in a space, but it can also be used to play sounds directly. Let's use the SoundSpace to play some music.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `MusicPlayer`
- Update `MusicPlayer` to the following:

```lang=csharp, name="MusicPlayer"
class MusicPlayer : ZilchComponent
{
  [Property]
  var MusicCue : SoundCue = SoundCue.BG_Arpeggios;
  
  function Initialize(init : CogInitializer)
  {
    this.Space.SoundSpace.PlayCue(this.MusicCue);
  }
}
```

- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `MusicPlayer`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

Notice how moving the player around has no effect on the volume level of the music, because it's playing directly through the SoundSpace, not a SoundEmitter. It might be a little bit too loud, though. That's easy to fix because the volume level of the SoundSpace can be controlled just like the volume of a SoundEmitter.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

- Update `MusicPlayer` to the following:

```lang=csharp, name="MusicPlayer (continued 1)"
class MusicPlayer : ZilchComponent
{
  [Property]
  var MusicCue : SoundCue = SoundCue.BG_Arpeggios;
  
  function Initialize(init : CogInitializer)
  {
    this.Space.SoundSpace.PlayCue(this.MusicCue);
    
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }
  
  function OnLogicUpdate(event : UpdateEvent)
  {
    if (Zero.Keyboard.KeyIsDown(Keys.Minus))
    {
      this.Space.SoundSpace.Volume -= event.Dt;
      Console.WriteLine("Music Volume: `this.Space.SoundSpace.Volume`");
    }
    
    if (Zero.Keyboard.KeyIsDown(Keys.Equal))
    {
      this.Space.SoundSpace.Volume += event.Dt;
      Console.WriteLine("Music Volume: `this.Space.SoundSpace.Volume`");
    }
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- Press key the `Space` bar to play the explosion sound, and hold key the `-` and `=` keys to decrease and increase the SoundSpace's volume

Now you can control the volume level of the output of the SoundSpace, but the volume of the explosion sound is affected too. This is because the SoundSpace applies its volume to every sound that plays in its space, whether positionally or not. There are a few different ways to control just the volume of an individual music cue (or any other SoundCue played non-positionally). Let's look at one of them.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 #  SoundInstances

A [ SoundInstance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown) is a class object that represents a specific occurrence of a SoundCue being played. It can be manipulated in Zilch, where its interface is very similar to those of both the SoundEmitter and SoundSpace components.

- Update `MusicPlayer` to the following:

```lang=csharp, name="MusicPlayer (continued 2)"
class MusicPlayer : ZilchComponent
{
  [Property]
  var MusicCue : SoundCue = SoundCue.BG_Arpeggios;
  
  var MusicInstance : SoundInstance;
  
  function Initialize(init : CogInitializer)
  {
    this.MusicInstance = this.Space.SoundSpace.PlayCue(this.MusicCue);
    
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }
  
  function OnLogicUpdate(event : UpdateEvent)
  {
    if (Zero.Keyboard.KeyIsDown(Keys.Minus))
    {
      this.MusicInstance.Volume -= event.Dt;
      Console.WriteLine("Music Volume: `this.MusicInstance.Volume`");
    }
    
    if (Zero.Keyboard.KeyIsDown(Keys.Equal))
    {
      this.MusicInstance.Volume += event.Dt;
      Console.WriteLine("Music Volume: `this.MusicInstance.Volume`");
    }
  }
}
```

Note how the `MusicInstance` member variable is used: the SoundSpace's `PlayCue` function actually returns a SoundInstance, but we didn't hang onto it before because we didn't need it. Now that we do want to use it, we can store it as a member and work with it later.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- Press key the `Space` bar to play the explosion sound, and hold key the `-` and `=` keys to decrease and increase the music's volume

These changes allow us to alter the music's volume independently from the volume of the sound effects.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Related Materials
 ##  Tutorials
- [actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/actions.markdown)
- [spaces](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/architecture/spaces.markdown)
 ##  Manual
- [ Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/launchernewproject.markdown)
- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
 ##  Reference
 ###  Classes
- [transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
- [camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown)
- [action](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/action.markdown)
- [space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/space.markdown)
- [soundspace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown)
- [soundemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown)
- [soundcue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundcue.markdown)
- [soundlistener](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundlistener.markdown)
- [soundinstance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown)

 ###  Events
- [#logicupdate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#logicupdate)

 ###  Commands
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)
- [Console](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#console)

 ##  Development Task
- {T1211}
 

 