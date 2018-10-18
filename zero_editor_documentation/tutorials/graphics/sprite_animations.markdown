This lesson covers how to import and use sprite sheets to create sprite animations

 # Learning Objectives
 - Importing sprite sheets
 - Defining each animation frame
 - Sprite animation parameters

 # Level Setup
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Player`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Scale  to `[2, 2, 2]`
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Renderer object
 - Under `ForwardRenderer`
  - Set ClearColor  to `[R:125, G:255, B:125, A:1.00]`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106281.png)


 # Importing a Sprite Sheet

Sprite animations are created out of a sequence of images displayed in quick succession. To accomplish this we use a Sprite Sheet; a image file that contains the sequence of frames corresponding to one or more animations.

- Download the following Sprite Sheet:



![RedPandaSpriteSheet](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106314.png)


- Import them into the project by dragging and dropping the files into the `Level Window`
- In the `Group Import Options Window`
 - Set ImportImages enum to `Sprites`
 - Press the `Import All` button



![ImportSpriteSheet](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106316.gif)


 # Creating Sprite Animations

Now that we have imported a sprite sheet, we need to separate the frames into their respective animations. The sheet we just imported has two animations; a walk animation that corresponds to the top 5 frames and a roll animation that corresponds to the remaining 7 frames.



![RedPandaAnimationFrames](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106388.png)


- In the `Library Window`
 - Under the SpriteSource  tag
  - `Double-Click` the RedPandaSpriteSheet texture resource
- In the `Sprite Source Editor Window`
 - Press the `Convert To Animation` button



![ConvertToAnimation](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106407.png)


- In the `Sprite Importer Window`
 - Set FramesPerRow  to `5`
 - Set NumberOfRows  to `3`
 - Left-click  frames 0 through 4 to select them
 - If you accidentally select a tile you don't want, right-click  it to deselect it
 - Set Name  to `Walk`
 - Press the `Add and Continue` button
 - Left-click  frames 5 through 11 to select them
 - Set Name  to `Roll`
 - Press the `Add and Close` button

(NOTE) **Frame Size vs. Frame Count:** When you set FramesPerRow , the Sprite Importer automatically calculates the FrameWidth  property, and vice versa. Likewise, when you set NumberOfRows , FrameHeight  is computed automatically, and vice versa. As a result, if you would rather specify the pixel dimensions of each frame in a sprite sheet than the number of frames, that's a perfectly valid option too.



![CreatingAnimations](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106325.gif)


 # Using Sprite Animations

Now that we've generated the animation resources, we can start using them with sprites.

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Player object
- In the `Properties Window`
 - Under [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
 - Set SpriteSource enum to `Walk`

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![WalkAnimatio](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106332.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Looking at the [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown) component on the property grid we find that the last 4 properties are dedicated to sprite animations. They are:

| Sprite Animation Properties |
|--------------------|-------------------------------------------------------------------------------------|
| AnimationActive checkBox | Whether the animation is playing currently (Both in editor and in game) |
| AnimationSpeed   | Scalar applied to the Frame Rate of the animation resource   |
| StartFrame           | What frame the animation should start from  |
| CurrentFrame      | The current active frame of the animation (cycles as the animation is playing) |

Let's add a component that lets us control the animation.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `PlayerAnimationController`
- In the `PlayerAnimationController` script
 - Update the `PlayerAnimationController` class to the following:

```lang=csharp, name="PlayerAnimationController"
class PlayerAnimationController : ZilchComponent
{
  [Dependency] var Sprite : Sprite;
  
  [Property]
  var WalkAnimation : SpriteSource = SpriteSource.Walk;
  
  [Property]
  var RollAnimation : SpriteSource = SpriteSource.Roll;
  
  [Property]
  var RollKey : Keys = Keys.Space;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(Zero.Keyboard, Events.KeyDown, this.OnKeyDown);
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnKeyDown(event : KeyboardEvent)
  {
    if(event.Key == this.RollKey)
      this.Sprite.SpriteSource = this.RollAnimation;
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    //If we are playing the roll animation
    if(this.Sprite.SpriteSource == this.RollAnimation)
    {
      //And it reaches its last frame (counted from 0 to 6)
      if(this.Sprite.CurrentFrame == 6)
      {
        //Play the walk animation
        this.Sprite.SpriteSource = this.WalkAnimation;
      }
    }
  }
}
```
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Player object
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `PlayerAnimationController`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

- Press `Space`



![WalkAndRoll](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106395.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Related Materials

 ## Manual
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Graphics/Sprites/Sprite.markdown)
- [Sprite Source Editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Graphics/Sprites/SpriteSourceEditor.markdown)
- [Sprite Importer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Graphics/Sprites/SpriteImporter.markdown)

 ## Code Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Transform.markdown)
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Sprite.markdown)
- [Cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Cog.markdown)
- [spritesource](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritesource.markdown)

 ### Commands
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)


 ## Development Task
- T1183
 

 