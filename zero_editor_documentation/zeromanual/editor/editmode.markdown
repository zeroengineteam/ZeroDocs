This section covers the basic differences between 2D and 3D editing modes in the engine.

 # Overview
As prototype projects were being developed with the Zero Engine, a shift was made to have strong 2D support. The engine features several 2D support elements, such as the ability to: set the [Physics](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics.markdown) to 2D, change the camera to orthographic, and use a special sorting mode for sprites. 2D mode is a setting that activates all these features by default.
Settings that 2D Mode changes on project startup:
* Default camera in the level is orthographic with Z depth based sprite sorting
* Level is created with 2D physics
  * Linear forces applied on the Z axis will not be integrated on objects.
  * During Collision Resolution angular forces will only be applied on the Z axis
* Editor Camera is changed to orthographic and set into Z plane mode

NOTE: In 2D Mode, objects can still have their Z Translation set to a value other than zero.

 ## Can I change my 2D project to 3D?


The setting is just defaults, so you can change any setting back. You can also use the [Command ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown) : [Mode3D](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#mode3d)/[Mode2D](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#mode2d). You can also click the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47018.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47020.png) buttos in the top left corner of the `name=Level Window, icon=window-restore`.

(NOTE)**Physics when switching to 3D mode:** Keep in mind that the  [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown)  will not change mode when you use the `Mode2D` or `Mode3D` command. These commands are intended to help with editing not change the foundation of a project.


 ## Collision
The engine and collision detection are still 3D. This z dimension is a nice way of creating complex layers of collision. You can have objects span multiple layers of collision or jump forward and back between layers, they just won't translate on the Z axis.

 # Related Materials
 ## Manual
- [Physics](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics.markdown)
- [PhysicsSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown)
- [Command ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/Commands.markdown)
 ## Code Reference
- [Mode2D](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#mode2d)
- [Mode3D](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#mode3d) 
  
  
  
  
  
  
  

 