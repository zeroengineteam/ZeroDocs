This page introduces the Zero Engine editor and user interface. It covers editor windows such as the `Objects Window`, `Properties Window`, `Library Window`, `Level Window`, and `Search Window`.


## Create a New Project

(NOTE)**COMMANDS:**  
[Commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) represent all actions you can perform as a user in the Zero Editor (such as [CreateSpriteText](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createspritetext), [BackupProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#backupproject), and [ExportGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#exportgame)).  Links are used throughout the lesson for refreshing your knowledge on how to do common essential tasks. View how to enter Commands in Zero by following the link provided in the tutorial!

It is recommended that you create a new project. If this is the first time you have run the Zero Engine you will already be in the Projects screen and can simply type in a name for your project.  If you are not on the new Projects screen, you can access it using the Project menu.  See the section [The Zero Launcher](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/Launcher.markdown)) for more information.

To create a new project follow these steps:
* [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [NewProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47627.png)


* In the launcher
  * Select `EMPTY 2D PROJECT` template
  * Enter a NAME  for the project
  * Enter a Project Folder directory (if the default is not sufficient) by either typing out you're preferred folder path or `left clicking` the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47629.png) button to the right of LOCATION .
  * `Left click` on the `CREATE PROJECT` button.


## Windows Overview



After creating a new project, the editor should look something like this:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47640.png) *The first, default view as the Zero Editor is opened*



### Level Window



The `Level Window` (located in the center of the editor as seen in the image above) is where you will manipulate objects to build levels.  The visible grid is a customizable visual to help place objects within the level editor view, but isn't visible in actual gameplay.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47647.png) *This is located in the top left corner of the `Level Window`* 


In a collapsible toolbar at the top of the `Level Window` are a few buttons for altering the view.
| Buttons                             | Purpose |
|-------------------------------------|---------------------------------------------|
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47649.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47653.png) | Toggles between 2D & 3D camera controls.    |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47655.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47659.png) | Toggles the editor camera's rendering mode between Orthographic and Perspective Projection. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47662.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47664.png) | With the camera options you can either reset the editor camera to its default settings, or align a selected camera with the editor's camera.  |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47666.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47668.png) | Toggles the grid line visuals in the editor. |


### Properties Window

When an object is selected, the properties of that object are accessible from the `Properties Window`.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47675.png) *The `Properties Window` showing the Components of the LevelSettings object*


The `Properties Window` is the primary means for editing or building objects and their [Components](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/components.markdown).



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47677.png) *This is located directly under the Properties tab in the `Properties Window`*


The Properties Navigational buttons allow for quick and efficient editing.
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47679.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47681.png) | These arrows allow you to navigate back and forth between recently selected items that have been shown in the `Properties Window`. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47683.png) | The Show Selection button, on first click, pans the camera to the object and on second click, zooms in the camera to frame the selected object in the `Level Window`. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47685.png) | The recent button pulls up a drop down list of the recently accessed items for selection. |


### Tools Window

This window contains several useful tools for managing various objects within the level. Settings for the current tool being used are also available here. You can switch tools from the drop-down selection or by using hotkeys `1` through `9`.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47716.png) *`Tools Window`*




![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47718.png) *Tools drop-down selection*



### Library Window



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47728.png) *`Library Window`*


Anything you add to the game using the [Add](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#add) command or through drag-and-drop importing is stored as a [Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/resources.markdown). All resources added to your project can be found in the `Library Window`.


### Objects Window

Every level contains objects. An object can represent the floor, a wall, enemies, the player, and many other things. There are a few different buttons in the `Objects Window` that you should know about:

* **Eyeball:** Toggles visibility of an object *only while in the editor.* Objects with the eye button disabled will be invisible in the editor, but still visible when the level is played.
* **Selection Lock:** The small lock button can be turned on and off to toggle the ability to select an object from within the editor. This is especially helpful if you do not want to accidentally move an object.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47720.png) *View of the eye and lock button in the `Objects Window`*


The objects in the `Objects Window` can be searched for by name using the search bar. This feature can be invaluable if you have a level populated with dozens, or even hundreds, of objects.  Each level has three objects by default:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47722.png) *Visible objects in the level by default*



## Other Windows and Bars

###Search Window
This powerful tool allows you to search for various things within the editor.  It also has several other uses such as selecting objects, opening archetypes, viewing properties, etc., that are accessible from here. For example, if you wanted to quickly access a script file, you can just open the search view and type in the name of the script to find it and begin editing.  Another important use of the `Zero Search Window` is for performing commands. See [Commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) for more information.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47726.png) *The `Zero Search Window` for performing commands*


There are three ways to pull up the `Zero Search Window`:

1. Click anywhere in the `Level Window` and press `Space`
2. From **any** window press `Ctrl + Shift + Space`
3. Click the `Zero drop-down` in the upper left-hand corner


### Console Window

Pressing `~` will open the `Console Window`. It should appear directly below the `Level Window`.  The console can also be cleared out by pressing `Ctrl + Delete` while in focus.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47730.png) *`Console Window`*


(NOTE)**"In Focus"**:
To be "in" a window requires that the window has "focus". To gain focus you need to click on the window itself. This ensures that all your keyboard input works as intended.


### Game Window

The `Game Window` is where your game actually runs inside the editor. You can test or play your game (or specific levels) here without having to create an executable. 
* [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown): [PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)

The `Game Window` should appear with its tab next to the `Level Window` tab:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47732.png) *`Game Window` displaying empty level*


* Close the `Game Window` by pressing the `X button` on the Game tab
* You can also press `Esc` or use [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown): [StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

WARNING:
It is a good practice to close the game window while editing levels.  There are some assets in the Zero Engine that can be changed by scripts running in the game session.


### Tool Bar



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47734.png)


The tool bar is located at the top left of the entire editor. Various buttons to perform common actions are located here.
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47736.png) | Saves the project and all the resources in your Library |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47739.png) | These buttons line up with hotkeys `1` to `5` and they represent the some of the most commonly used tools for editing objects in the `Level Window`. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47742.png) | These are correspond to other less common Tools that are available. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47744.png) | These open windows in the Editor, such as  the `Library Window` and the Add Window. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47746.png) | These buttons allow you to run your game from the current level, pause, step through frame by frame, or stop executing the game, covering keys `F5` to `F8`. |
| ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47748.png) | These buttons are for downloading content and reporting bugs. |

In order to find out more about the function of each button, you can hover over them to get a pop-up tool tip. 



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47750.png)


All Tool Bar buttons have equivalent commands in the `Zero Search Window`.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47752.png)


The game session can be played, paused, stepped through, and stopped with the keys `F5` through `F8`. `F9`, `F10`, and `F11` are also engine specific hotkeys. `F9` will open the edit in game window for the first space, allowing objects to be edited in the scene while the game is running. `F10` will toggle whether the cursor is trapped, meaning it is made invisible and locked to the center of the screen. `F11` toggles fullscreen mode for the currently focused window.


### Menu Bar



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47756.png)

The menu bar includes a catagorized set of commands in the form of drop-down menus.


## Reopening Windows & Docking

The `Zero Search Window` can be used to reopen closed windows and tabs.  Once reopened, a window can dragged onto another location, a process known as "docking". Docking location options are indicated by the editor with light blue regions as another window is hovered over that location.



![Editor_DockingLibraryWindow](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47754.gif) *Docking the `Library Window` to the upper right-hand corner*


 ## Related Materials
 ### Manual
- [The Zero Launcher](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/Launcher.markdown)
- [Components](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/components.markdown)
- [Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/resources.markdown)

 ### Code Reference
- [CreateSpriteText](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createspritetext)
- [BackupProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#backupproject)
- [ExportGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#exportgame)
- [NewProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
- [Add](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#add)
- [PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame) 

 