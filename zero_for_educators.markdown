NOTE: This page is intended as a workshop for a trained instructor to teach potential Zero Engine Educators.

 # Intro
This section outlines a workshop on entry level game development education through the Zero Engine.

- Welcome
- Instructor background
- Trainee background
- Goals
 - Basic Zero Engine comprehension
 - Basic intructional knowledge of curriculum.
 - Feed back
 - Identify educator goals
 - Identify requirements and constraints of the educational context

 ## Zero Engine

The Zero Engine is a professional grade 3D game engine developed in DigiPen's R&D department. Let's start with with an overview of some highlevel

- Launcher
 - Builds
- Editor
 - UI
 - Text Editor
 - Customization
 - Tags
 - Commands
- Architecture
 - Components
 - Objects
 - Resources
 - Tools
- Graphics
 - Physically Based Rendering
- Physics
 - Kinematic
 - Dynamic
- Audio
 - 3D
- Scripting (Zilch)
 - Simple
 - Advanced

 ### Demos
- Physics Demo rFRIC
 #### Rube Goldbergs


![RubdGoldberg_Dominos](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93695.exe)



![RubeGoldberg_FullAdder](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93700.exe)

 #### Vapor


![10_Vapor](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93368.mp4)

 #### Aquarius


![Aquarius Trailer](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93389.mp4)

 #### Frozen Masquerade


![FrozenMasquerade_Trailer](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93390.mp4)

 #### Orpheus


![Orpheus - DigiPen Institute of Technology](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93426.mp4)

 #### Super Space Blank


![SuperSpace_-branded](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93427.mp4)

 #### The Lift


![The Lift - DigiPen Institute of Technology](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/93447.mp4)


 ## ZeroHub
Zerohub is the open source platform/site for Zero Engine developement and education.

- Open source platform
 - Tasks
 - Projects
 - Documentation
 - Source
- Support
 - Bug Reporting
 - Feature Requests
 - Demos
- Open Source Contribution
 - Editor
 - Documentation
 - Website/Platform (Phabricator)




 # Tutorials
The tutorial section is the bulk of the content intended for new students. Much of the workshop 
 ## [Tutorial Sequence](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/tutorial_sequences.markdown)
 ### [Beginner I](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/tutorial_sequences.markdown#beginner-i)

 ### [Beginner II](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/tutorial_sequences.markdown#beginner-ii)

 # [Manual](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown)

 # Projects
The following are suggested projects to be implemented after completing each set of the #basic_tutorials.

 ## Rube Goldberg Machine
After completing the #beginner_i tutorials students should be able to implement a simple version of a Rube Goldberg machine. Unlike the following projects the Rube Goldberg machine in not modelled after any paticular game and has many degrees of freedom. It is suggested that you require students to utilize the instances of each of the following features taught in the #beginner_i tutorials.

- Physics Effects
 - Applied to LevelSettings object
 - Applied to a [Region](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown)
- Physics Materials
 - Restitution
 - Friction
 - High Priority
- Hierarchies

 ## Pong
After completing the #beginner_ii tutorials students should be able to implement a simple version of Pong.
- Paddles
 - Basic Input
 - Object Movement
 - Collision Detection
 - Physics Materials
- Ball
 - Physics Materials
 - Random Direction
- Score
 - SpriteText


 ## Asteroids
After completing the #beginner_iii  tutorials students should be able to implement a simple version of Asteroids.

- Player Ship
 - Input
 - Movement
 - Firing
 - Screen Wrapping
 - 2D Rotation
- Asteroids
 - Archetypes
  - Construction
  - Runtime Spawning
   - Timers
   - Position



![Asteroids](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94408.zip)


 ## 2D Platformer
After completing the #beginner_iv tutorials students should be able to implement a simple 2D platformer.

- Player
 - Input
 - Movement (use the swept controller)
 - Health
 - Jumping
- Checkpoints
 - Respawning
- Simple Enemies
 - Patrol
 - Destroy/Respawn on Collision

 # External Materials and Resources
 ## Audio
- [Audacity](http://www.audacityteam.org/)

 ## Art
- [Open Game Art](https://opengameart.org/)
- [Kenney Sprite Assets](https://opengameart.org/)

 ## Acceptable Asset Licenses
- [CC0 ](https://creativecommons.org/share-your-work/public-domain/cc0/ ) (Creative Commons V0)
- [MIT ](https://en.wikipedia.org/wiki/MIT_License )

 ## Editor Reference
[Text Editor Hotkeys](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/texteditor/texteditorhotkeys.markdown) 

 