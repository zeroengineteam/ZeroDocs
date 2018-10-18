[Space](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/space.markdown) is the infinite three-dimensional extent in which objects and events have relative position and direction. It consists of 3 dimensional axes and time.

Spaces in the Zero Engine are containers for game objects. When a level is loaded, all the game objects from that level are put into a space. Also, when you create a game object in code, you must put it into a space, usually the same one that the level was loaded into. In a simple game you only have one space, which is where all your game objects go. Each space has its own instances of the core systems of the engine: graphics, physics, etc. Because of this, game objects in two different spaces will not collide or otherwise physically interact. Game objects in different spaces are rendered separately, but can be layered, such as when using one space for level game objects and another for UI game objects. Creating a separate space for UI game objects is one of the most common uses of multiple spaces in a game.

 # Using the Space
 ## Creating a Space
You can create a space through the [GameSession](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/objects/gamesession.markdown) object.

```
    class SpaceCreator : ZilchComponent
    {
      [Property]
      var MySpaceArchetype : Archetype;
      
      [Property]
      var MySpaceName : String = "MyNamedSpace";
      
      var MyNewSpace : Space;
      
      var MyNewNamedSpace : Space;
      
      function Initialize(init : CogInitializer)
      {
        //Here we create an unnamed Space object
        this.MyNewSpace = this.GameSession.CreateSpace(this.MySpaceArchetype);
        //Here we create a Space object named "MyNamedspace"
        this.MyNewNamedSpace = this.GameSession.CreateNamedSpace(this.MySpaceName, this.MySpaceArchetype);
      }
    }

```


Naming a space is not absolutely necessary, if you have a good system keeping track of the spaces you are creating. However, naming your space is a good general practice as you'll find when trying to access Spaces you have created.

 ## Accessing a the Space
You can access the Space object from scripts via any component or Cog:

```
  class ExampleComponent : ZilchComponent
  {
    // Accessing the Space object through the component
    var CurrentSpace : Cog
    {
      get { return this.Space; }
    }
    
    // Accessing the Space object through the component's object
    var AlsoCurrentSpace : Cog
    {
      get { return this.Owner.Space; }
    }
    
    function Initialize(init : CogInitializer)
    {
      // If we compare the values of the to properties which access the
      // Space object through different objects we can prove that they
      // are accessing the same Space object.
      if(this.CurrentSpace == this.AlsoCurrentSpace)
      {
        Console.WriteLine("These properties reference the same Space object.");
      }
    }
  }

```


Accessing the Space this way will give you a reference to the Space that the object `ExampleComponent` is attached to exists in.
n some games you may have multiple spaces in order to implement certain features such as an in game HUD. In situations such as this you must store a reference to the `HUDSpace` on creation in order to access it later.

 # Space Components
Spaces have special space components that can not be removed. These are core engine components for containing different aspects of the game objects like physics, graphics, and sound.

Spaces are stored as [Archetypes](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/archetypes.markdown) and can be modified to change the properties of a space.

To access the space of the current level Press: 

 - In the `name=Level Window, icon=window-restore`
  - Press `shift + s`

**Or**

 - In Select drop down
  - Click Select Space

When opened, a space should look something like this:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46992.png)


By default a space has four components TimeSpace, GraphicsSpace, PhysicsSpace, and SoundSpace, but if needed you may add more by creating a new space archetype and adding the desired components. In each component of the space properties can be found that will affect the entire space.

NOTE: The ReactiveSpace component is deprecated and changes made to it will have no effect on the Space or how using the Reactive component works.


 # Events Dispatched On The Space Object


| Event Name                | Type                       | Description                                                         |
|---------------------------|----------------------------|---------------------------------------------------------------------|
| PhysicsUpdateFinished     | [objectevent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/objectevent.markdown) | Dispatched immediately after physics has finished updating.         |
| LogicUpdate               | [updateevent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/updateevent.markdown) | Dispatched after the major systems's updates (doesn't run in editor)|
| FrameUpdate               | [updateevent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/updateevent.markdown) | Dispatched after the engine update. Runs in editor.                 |

---

 # Related Materials
 ## Manual
- [Archetypes](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/archetypes.markdown)
- [GameSession object](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/objects/gamesession.markdown)
 ## Code Reference
- [timespace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/timespace.markdown)
- [graphicsspace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/graphicsspace.markdown)
- [physicsspace](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/physicsspace.markdown)
- [soundspace](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundspace.markdown)
- [objectevent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/objectevent.markdown)
- [updateevent](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/code_reference/class_reference/updateevent.markdown)
 

 