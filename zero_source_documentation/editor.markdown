The editor is created once and manages:

- All windows and docking (done through the base MultiDock class)
- The current level(s) being edited
- All running game sessions
- Selection
- Operation queue (undo/redo)
- Commands
- Tools

Project loading
 ### 
Why we restart editor when loading projects (meta flush)

Commands
 ### 
- Requires documentation

Commands from Data
---
Commands are loaded from the Data\Commands.data file in the Zero repository. These commands are then bound in C++ to specific functions on the editor.

Cog Commands
---
CogCommands are just Cogs that are marked as a command object, and when the command is invoked, the 'ExecuteEvent' event will be sent on the cog. This allows for users to create custom commands without learning a new system. They use what they're used to and just respond to a different event. The command Cogs are all created in a single Space (named "CommandSpace") that lives under the editors game session.

There are two ways a CogCommand can be created:

- A Component with the [Command] attribute with the attribute parameter 'autoCommand' set to true.
- An Archetype with tag "Command".

Command Context
---
This gives commands more information about the circumstances they were invoked in, such as which viewport has focus when the command is invoked.

Command 'Active' state
---
Used for Tools and toggle-able commands. Example: Tools have Commands that enable them, so when the tool is selected, that command is now considered 'Active' until another tool is selected. This allows the IconButton in the Ui to display that the tool is active.

Gizmos
 ### 
- Requires documentation

Basic Gizmos
---
- Requires documentation


Tools
 ### 
- Requires documentation

Events
---
Connect to this.Owner for all events. They will all be sent directly to the tool when the tool is selected.

- Events.ToolActivate   - Sent when the tool has been selected
- Events.ToolDeactivate - Sent when the tool has been de-selected
- Events.ToolDraw       - Sent every frame to debug draw

- Events::MouseDown
- Events::MouseMove
- Events::MouseUpdate
- Events::LeftMouseDown
- Events::LeftMouseUp
- Events::DoubleClick
- Events::RightMouseDown
- Events::RightMouseUp
- Events::MiddleMouseDown
- Events::MouseScroll

- Events::KeyDown
- Events::KeyUp


Operations
 ### 
- Requires documentation

Custom Tools
---
- Requires documentation

Viewports
 ### 
- Requires documentation

EditorViewport
---
- Requires documentation

GameViewport
---
- Requires documentation

Notifications
 ### 
- Requires documentation

Windows
 ### 

Text Editor
---
- Requires documentation

Main Property Grid
---
- Requires documentation

Resource Library
---
- Requires documentation

Object View
---
- Requires documentation

Console
---
- Requires documentation

Tools Window
---
- Requires documentation

Resource Editors
---
- Requires documentation

Downloads
 ### 
- Requires documentation

Automation
 ### 
- Stress Test
- Coming soon

Animator
 ### 
- Requires documentation

Rich Animation
---
- Requires documentation
- Fbx -> RichAnimation issues	

Animation Editor
---
- AnimationEditorData

Controls
---
- Requires documentation


#### Track View


- Requires documentation


#### Scrubber

- Requires documentation


#### Graph


- Requires documentation


#### Dope Sheet


- Requires documentation


#### Controls


- Requires documentation
 

 