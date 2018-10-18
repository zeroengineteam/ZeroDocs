This lesson introduces the Zero Engine editor and user interface. It covers editor windows such as the `Objects Window`, `Properties Window`, `Library Window`, `Level Window`, and `Search Window`.

 # Learning Objectives

- Elements and features of the #zero_editor 
- Basic #zero_tutorials style

 # Tutorial Structure
In Tutorials, instructions are laid out in a specific way to make them easier to understand.
For example:


> - In the `Object Window`
>  - [Select](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) the Player object object
> - In the `Properties Window`
>  - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown):
>  [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
>  - Under [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
>   - Set AllowSleep button to `false`



Each level of indentation represents a subsection of the window you are already in, where the base is the Editor itself. This makes it easier for you to know where to look in the editor for the information you seek. As the lessons progress some common steps will be cut for brevity, for instance:



> - In the `Level Window`
>  - Press `Space`  
> - In the `Search Window`
>  - Type `CreateSprite`
>  - Press `Enter`



will be shortened to:
    - [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown): [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)

This significantly reduces the amount of reading, and while still providing a reference to the full process should you need a refresher.

 # Create a New Project

It is recommended that you create a new project. If this is the first time you have run the Zero Engine you will already be in the Projects screen and can simply type in a name for your project. If you are not on the new Projects screen, you can access it using the Project menu.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106519.png)


- Open the Zero Launcher
- In the `Project Window`
 - Select `EMPTY 2D Project` template
 - Enter a name for the project in the Name field
 - Enter a Project Folder directory (if the default is not sufficient) by either typing or left clicking the browse button on the right of the field.
 - Left Click the `Create Project` button

Alternatively, you can create a new project from within the editor by using [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)

NOTE:   
 [Commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) represent all actions you can perform as a user in the Zero Editor. Page numbers are listed throughout the lesson for refreshing your knowledge on how to do common essential tasks. View how to enter Commands in Zero by going to the page number provided in the tutorial!

 # Windows Overview

After creating a new project, the editor should look something like this:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/106521.png)


 # Level Window

The `Level Window` (located in the center of the editor as seen in the Window Overview section above) is where you will manipulate objects to build levels. The visible grid is a customizable visual to help place objects, but doesn't show in actual gameplay. 


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47166.png)

| Buttons To Alter Level View |
|--|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47184.png)  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47186.png)| Toggles between 2D & 3D camera controls|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47188.png)  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47190.png)| Toggles editor camera's render mode between Orthographic and Perspective|
|![Camera](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47182.png)|With the camera options you can either reset the editor camera to its default settings, or align a selected camera with the editor's camera|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47192.png)  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47194.png)|Toggles the grid line visuals in the editor|

 # Objects Window

Every level contains objects. An object can represent the floor, a wall, enemies, the player, and many other things. There are a few different buttons in the `Objects Window` that you should know about:
-   **Eyeball:** Toggles visibility of an object *only while in the editor.* Objects with the eye button disabled will be invisible in the editor, but still visible when the level is played.
-   **Selection Lock:** The small lock button can be turned on and off to toggle the ability to select an object from within the editor.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47198.png)


The objects in the `Objects Window` can be searched by name using the search bar. Each level has four objects by default:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47201.png)

-   Click on the LevelSettings object object to select it



![Select](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47205.gif)


 # Properties Window

When an object is selected, the properties of that object are accessible from the `Properties Window`.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47207.png)


The `Properties Window` is the primary means for editing or building objects. An object being comprised of multiple **components**.

NOTE: **Component** is a chunk of functionality or small bucket of data. An object's behavior and purpose depends upon what components it contains. Game objects are made up of different components. More details about components will be covered in future lessons.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47209.png)


|Properties Navigation Buttons|
|--|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47211.png)  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47213.png)|These arrows allow you to navigate back and forth between recently selected items that have show in the `Properties Window`|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47217.png)|The Show Selection button, on first click, pans the camera to the object and on second click, zooms the camera in to frame the object in the `Level Window`|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47219.png)|The Recent button pulls up a drop down list of the recently accessed items for selection|

 # Library Window



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47221.png)


Anything you add to the game using [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [Add](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown) or through drag-and-drop importing is stored as a resource. All resources added to your project can be found in the `Library Window`. You'll learn more details about resources in future lessons.

 # Search Window

This powerful tool allows you to search nearly anything within the editor. Perhaps its most important use is executing [Commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown).



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47223.png)


(NOTE) **"Do This + That":**
    The `+` symbol can be read as "and" when used to describe button combinations. It means you should do all the actions "added" together simultaneously. 
   Press `Ctrl + C` to copy, would mean hold down `Ctrl` on your keyboard then press `C` to perform the copy action.

There are three ways to bring up the Zero `Search Window`:

#  Click anywhere in the `Level Window` and press `Space`

# From **any** window press `Ctrl + Shift + Space`

#  Click the Zero Search Button in the upper left-hand corner




![SearchButton](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/88506.png)


 ## Reopening Windows & Docking

With its numerous commands the `Search Window` provides many crucial functions such as those that reopen closed windows and tabs. 
-   Click the x on the Library tab to close the `Library Window`:


![CloseWindow](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47227.gif)

-   Press `Ctrl + Shift + Space` to open the `Search Window`
   Search for the Library command by typing `Library`, then hit enter (or click on the Library command directly) to open the `Library Window`

This same process can be used to reopen many of these key windows. Once reopened, you can use the drag and drop technique on the tab at the top of the window to "dock" it back into the same starting configuration. Docking locations are indicated by the editor with light blue regions as you hover over them. When you find the one you want to dock to, release the left mouse button:


![DockWindow](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47233.gif)


 # Console Window

- Press the Tilde `~` key to open the `Console Window`


![consolewindow](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1444.png)


NOTE: To be "in" a window requires that the window has "focus". To gain focus you need to click on the window itself. This ensures that all your keyboard input works as intended.

- In the `Console Window`
  - Press `Ctrl + Delete` to clear the console
- In the `Level Window`
  - Press `Space`
 - Type the [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [SaveProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#saveproject)
 - Press `Enter`
A message telling you the project was saved is displayed in the `Console Window`.
When console output is referenced in future lessons it will be shown like this:

```name=Console Output
Saved level file 'Level'.
Uploaded to archetype MyProject.Game.
Saved : Project and all scripts saved.
```

 # Game Window

The `Game Window` is where your game actually runs inside the Zero Engine editor. You can test or play your game (or specific levels) here without having to create an executable. 
- [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown): [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)

There are multiple ways to run the game in the editor.
 - Press key `F5` on the keyboard 
 - Press the Play button button in the `Tool Bar`
 - [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
 - `Project Menu  > Play Game`

The `Game Window` tab should appear in a tab next to the Level Window tab:


![gamewindowtabweb](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1427.png)


The `Game Window` should not show anything but a blank screen right now because we haven't added any visible objects to our level yet:


![emptywindowweb](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1442.png)


-  Close the `Game Window` by pressing the `X` button on the Game tab
- You can also press `Esc` or use [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown): [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)
  It is a good practice to close your game window promptly. Editing levels while the `Game Window` is open can cause erratic behavior, undefined behavior, or errors. 
- Click on the Level tab to return to the `Level Window`

 # Tools Window

This window contains several useful tools for using the Zero Editor. These tools are for managing various objects within the level. Settings for the current tool being used are also available here. You can switch tools from the drop-down selection or by using hotkeys.
-   Click anywhere in the `Level Window` then press `1` on your keyboard. This is a hotkey for switching to the SelectTool.


![selecttool](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1445.png)


Click on the drop-down selection in the `Tools Window` to display a list of tools you can use:


![toolsselection_png](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1439.png)


 # Tool Bar



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47235.png)


| The Tool Bar|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47237.png)|Saves the project and all the resources in your Library|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47239.png)|These buttons line up with hotkeys 1-5 and they represent some of the most commonly used tools for editing objects in the `Level Window`|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47241.png)|These correspond to other, less common tools that are available|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47243.png)|These open windows in the Editor, such as the `Library Window` and the Add Window|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47245.png)|These buttons allow you to run your game from the current level `F5`, pause `F6`, step through frame by frame `F7`, or stop executing the game `F8`|
|![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47247.png)|These link to outside resources to get content, give bug reports, and request support.|

In order to find out more about the function of each button, you can hover over them to get a pop-up tool tip. 


![tbsavetip](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1447.png)

You can reach all the same functionality by searching in the `Search Window`.   


![tbsavesearch](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1448.png)

You may have noticed that you can play, pause, step through, and stop your game with the `F5` - `F8` function keys. `F9`, `F10`, and `F11` are also engine specific hotkeys. `F9` will open the edit in game window for the first space, allowing you to edit objects in the scene while the game is running. `F10` will toggle whether the cursor is trapped, meaning it is made invisible and locked to the center of the screen. `F11` toggles fullscreen mode for the currently focused window.

 # Menu Bar



![menubar](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1436.png)

The menu bar includes commands for project manipulation and exporting your game under `File`, quick create options for getting things on the screen fast under `Create`, and the ability to reopen closed windows via `Windows`.
See [Executing Commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) for information.

 # Related Materials

 ## Manual
- [Components](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/components.markdown)
- [ Zilch User Documentation](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero.markdown)

 ##  Tutorials
- [BasicComponents](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/architecture/BasicComponents.markdown)
- [CustomComponents](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/scripting/CustomComponents.markdown)

 ## Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Transform.markdown)
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Sprite.markdown)
- [ZilchScript](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ZilchScript.markdown)
- [ Console](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/console.markdown)

 ### Commands
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)
- [New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
- [SaveProject](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#saveproject)
 

 