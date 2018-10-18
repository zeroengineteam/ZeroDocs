This lesson focuses on teaching the very basics of the engine: creating objects, running the game, basic commands, searching, and manipulating objects by scaling, rotating, translating.


 # Learning Objectives


 - Game object creation
 - Game object names
 - Editor commands
 - Object manipulation with editor tools


 # Level Setup


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template

Here is a new empty level:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46948.png)


*An "empty" 2D level*


Notice that the level isn't actually empty. A quick look into the `Objects Window` shows us that the level has a few game objects already in it.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46947.png)


*The `Objects Window` showing the objects present in the otherwise-empty level*


We'll cover these in more detail in future tutorials.

 # Create a Game Object

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)



![CreateSprite](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46945.gif)


*Creating a Sprite object via the `Create Menu`*


The Sprite object object can now be found in the `Objects Window`:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46949.png)


*The Sprite object listed in the `Objects Window`*


- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object

NOTE:
 If the `Properties Window` is not visible, then enter the [Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Properties](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#properties) in the `Search Window`. (Remember you can open the ` Search Window` from any where in the engine using `Ctrl + Shift + Space`.)

The properties of the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component attached to the object can be found in the `Properties Window`:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46950.png)


*The properties of the Sprite object in the `Properties Window`*

- In the `Properties Window`
 - Click  on the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component



![Under](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/85621.gif)


*Expanding the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component in the `Properties Window`*


(NOTE)**Under**: When accessing properties of a paticular component we use the term **Under**, as the properties are found **under** the component title in the `Properties Window`. For instance, *Under the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component* {icon long-arrow-right} //Set Scale  to `[2, 2, 1]`//.


 #  Renaming an Object


- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Square`


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46952.png)


*Renaming the Sprite object*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

Here is how the game should look:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46336.png)


*The `Game Window`*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)


 #  Tools


To help you create and manipulate objects, Zero Engine provides tools that can be found at the top of the `editor window` within the `Tool Bar`.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/86287.png)


Let's take a look at some of the more common tools:


 ## Select Tool


The Select Tool allows you to select objects in the `Level Window` by clicking on them.

- In the `Tool Bar`
 - Click  the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/86293.png) button
- In the `Level Window`
  - Click  on the Sprite object object



![Select](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/86291.gif)


This is an equivalent operation of selecting the object in the `Objects Window`


 ##  Translate Tool


The Translate Tool is used to move objects around the level.

- In the `Tool Bar`
 - Click  the ![translategizmo](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/110.png) button

You should see colored arrows along the X (red), Y (green), and Z (blue) axes of the object.

- `Click and drag` the colored arrows to move the object along the corresponding axes.



![Translate](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46953.gif)


Notice that in the `Properties Window`, the Translation  values are changing while you move the object.


 ##  Rotate Tool


The Rotate Tool is used to rotate objects.

- In the `Tool Bar`
 - Click  the ![rotategizmo](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107.png) button
- `Click and drag` one of the circles (red, blue, or green).



![Rotate](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46954.gif)


This rotates the object around its X (red), Y (green), or Z (blue) axes. In 2D, we usually just rotate around the Z-axis. Notice that in the `Properties Window`, the Rotation  values are changing while you rotate the object.



 ##  Scale Tool


The Scale Tool is used to scale objects.

- In the `Tool Bar`
 - Click  the ![scalegizmo](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108.png) button
- `Click and drag` along the colored axes

This scales the object along its X (red), Y (green), or Z (blue) axis.



![Scale](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46955.gif)


Notice that in the `Properties Window`, the Scale  values are changing while you scale the object.

NOTE: Zero Engine does **not** support negative scale for objects.

 # Related Materials

 ## Manual
- [COGs](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown)
- [Editor Commands](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands.markdown)

 ## Code Reference
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
 

 