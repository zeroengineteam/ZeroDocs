The LevelSettings object is a [Cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/cogs.markdown) of which there is one unique instance per Level. It serves as a globally accessible object from a variety of object types such as Components or other Cog. Unlike any other Cog there is no way to instantiate a LevelSettings object.

 # Common Uses
 - Adding level specific [physics effects](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown).
 - Adding custom components which need to be globally accessible in a level by any other components that exist in the level.

 # Using the LevelSettings Object

 ## Accessing the LevelSettings Object In Editor

NOTE: **Initialization Order** Notice that because the LevelSettings object is always the first object in the [Object Window](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorui.markdown) (and cannot be reordered) it will always be the first object to be created and initialized when the level is loaded into the Space. This can be very useful when implementing logic which depends on being initialized before related components on other objects in the level.


The LevelSettings object will always be the first object in the Object Window making it easy to find in editor.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46988.png)


Since the LevelSettings object lacks any Graphics or Physics based representation in the level, the only way to select and modify its components in the editor is through the Object Window.

NOTE: **LevelSettings & Hierarchies**  While parenting can often be useful with objects that do not have transforms, in the case of the LevelSettings object, parenting has been deactivated.

 ## Accessing the LevelSettings Object In Script
The LevelSettings object may be accessed from scripts via any component or Cog:

```name=LevelSettings Access Example, lang=csharp
class ExampleComponent : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    // Accessing the LevelSettings object through the component
    var thisLevelSettings = this.LevelSettings;
    // Accessing the LevelSettings object through the component's object
    var ownerLevelSettings = this.Owner.LevelSettings;
    // Accessing the LevelSettings object through the Space object
    var spaceLevelSettings = this.Space.LevelSettings;

    // If we compare the values of the properties which access the LevelSettings
    // object through different objects (component, component's object, and 
    // space), we can prove that they are accessing the same LevelSettings object.
    if(thisLevelSettings == ownerLevelSettings
    && ownerLevelSettings == spaceLevelSettings)
    {
      Console.WriteLine("These variables reference the same LevelSettings object.");
    }
  }
}
```

 ## Default Components of LevelSettings


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46990.png)


 ### GravityEffect & DragEffect
Physics Effects are built in components that implement a piece of common physics-based functionality such as the [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/forceeffect.markdown) or the [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown) components that are attached to the LevelSettings by default. Each physics effect component may perform the logic on different spatial scopes depending on which object is attached to. When a physics effect component is attached to the LevelSettings object it is applied to all objects in that level. This allows one to implement level wide effects with any of the built in physics effects as is done by default with GravityEffect and DragEffect.

 ### GridDraw
The [griddraw](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/griddraw.markdown) component is a simple debug drawing component. It uses Zero's buit in GridDraw component is a simple debug drawing component. It uses Zero's buit in [debugdrawing](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/scripting/debugdrawing.markdown) to create a customizable unit grid in the Level Window.

 ## Custom Components
The LevelSettings object is often a very convenient object on which to attach certain custom Zilch components. Imagine a scenario in which a function is implemented for a friendly AI which needs to return an enemy to attack. If all the enemies exist independent of any other object or component, there may be no immediate path from which to access all enemies from the AI.

A common technique is to add an `EnemyManager` component to the LevelSettings object which has a member of type `Array[Cog]` called `EnemyList`. By attaching this component to the LevelSettings object all objects, including the enemies, are given access to the `EnemyManager` component. If the enemies are implemented so that they add themselves to the `EnemyList` when they are initialized and remove themselves when they are destroyed, there now exists a reliable way of accessing a complete list of all existing enemies.

While the above example may not be applicable to all games, it demonstrates the usefulness and flexibility that the LevelSettings object may grant.

 ## Events Dispatched On The LevelSettings Object


| Event Name       | Type                                | Description                                                       |
|------------------|-------------------------------------|-------------------------------------------------------------------|
| EnterView        | [graphicalevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphicalevent.markdown) | Dispatched if [cameraviewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cameraviewport.markdown) is attached to the LevelSettings object. |
| ExitView         | [graphicalevent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphicalevent.markdown) | Dispatched if [cameraviewport](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cameraviewport.markdown) is attached to the |

---

 # Related Materials
 ## Manual Pages
- [Cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/cogs.markdown)
- [Editor UI](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorui.markdown)
- [Debug Drawing](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/scripting/debugdrawing.markdown)
- [physics effects](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)

 ## Code Reference
- [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) 
- [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown) 
- [GridDraw](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/griddraw.markdown) 
 

 