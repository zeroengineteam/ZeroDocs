A level is resource that stores a set of objects which will then be created later when the level is loaded. Levels can be loaded into a space in order to create all objects saved to the resource. Levels can be edited using several tools, especially those found via the [Editor UI](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorUI.markdown).

 # Using Levels
 ## Creating a Level
A new level can be added by using the Add command ([Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [Add](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#add) or clicking on the Add button button) followed by selecting Level drop-down menu. The newly-created level will open in the Level Window and allow for the manipulation of objects to build game levels. At creation the level will only have the default objects inside it: `LevelSettings` and a few other object from the level template you select.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47014.png)


 - The [LevelSettings](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/objects/levelsettings.markdown) object is a cog that has a single unique instance per level that cannot be deleted or duplicated. It has several components attached in order to run various effects in the level, such as gravity.

The background grid will also be turned on. The grid is there to help place objects within the level editor but will not be visible during gameplay, and can be turned on and off by using the toolbar in the top left corner of the Level Window.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47016.png) *The collapsible toolbar has a few buttons for altering the view.*



| Buttons                             | Purpose |
|-------------------------------------|---------------------------------------------|
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47018.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47020.png) | Toggles between 2D & 3D camera controls.    |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47024.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47022.png) | Toggles the editor camera's rendering mode between Orthographic and Perspective Projection. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47027.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47029.png) | With the camera options you can either reset the editor camera to its default settings, or align a selected camera with the editor's camera.  |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47031.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47033.png) | Toggles the grid line visuals in the editor. |

 # Levels vs. Spaces
While levels are resources that store object data to later be loaded, spaces are where those objects are placed upon creation. This allows multiple spaces to load multiple levels at once, which is used to create HUD or UI elements, or to pause the main game while still allowing pause menus to function properly. 

```
// The level made with all the Pause Menu UI elements
[Property]
var PauseLevel : Level;

// A property to hold a Space archetype used to create the Pause level
[Property]
var PauseSpaceArchetype : Archetype;

// A variable used as a reference for the Space holding the pause menu
var PauseSpace : Space = null;

function Initialize(init : CogInitializer)
{
}

function Pause()
{
    // Create a new named Space for the Pause Menu
    this.PauseSpace = this.GameSession.CreateNamedSpace("PauseSpace", this.PauseSpaceArchetype);
     // Load the Pause Menu level in the newly created Space
    this.PauseSpace.LoadLevel(this.PauseLevel);
}

function UnPause()
{
    // If the PauseSpace exists, destroy it along with the Pause level
    if (this.PauseSpace != null)
        this.PauseSpace.Destroy();
}
```


This code snippet gives an example of having two levels exist at once. By giving it a `Space` archetype and `level` to load and then calling the `Pause()` function in a ZilchScript, it will create a new Space and load the new level without destroying the currently existing one. The `Unpause()` function will do the reverse, and destroy the level and Space. 

---

 # Related Materials
 ## Manual
- [Editor UI](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorUI.markdown)
- [Spaces](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/objects/spaces.markdown)
- [CamerasViewportsRenderers](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Graphics/CamerasViewportsRenderers.markdown)
- [Level Settings](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/objects/levelsettings.markdown)
 

 