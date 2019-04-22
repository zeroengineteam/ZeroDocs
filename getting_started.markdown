  Welcome to ZeroHub, the open source project development hub for the Zero Engine community. The Zero Engine is a powerful simulation engine custom built in C++ by [DigiPen](https://www.digipen.edu/) [Research & Development](http://www.digipenresearch.com/), a team of DigiPen graduates.

 #  [Download the Engine](httpa://downloadlauncher.zeroengine.io )
 - [min_specs.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master//Users/beepboopowner/Desktop/AJ/DP/getting_started/min_specs.markdown)

 # Installing the Zero Engine (and Zero Launcher)

Zero Engine is downloaded through a separate application called the Zero Launcher, which provides features such as multiple build installation and access, new project creation, and a browser for recent projects.

 - [Learn how to use the Zero Launcher](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/launcher.markdown).

 # Zero Engine Features
The Zero Engine can be used to make simulations of any kind. Projects range from simple prototypes to professional 2D and 3D games, simple physics or graphics demonstrations to robust, realistic simulations. Versatility of the engine is made possible by the features in the following sections:

 ## [Editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor.markdown)
 - A discrete [launcher](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/launcher.markdown) that provides access to all project and engine builds
 - [Editor modes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editmode.markdown) customized for 2D and 3D projects
 - Full-featured [text editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/texteditor.markdown) with dozens of hotkeys and configuration options 

 ## [Architecture](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture.markdown)
 - [Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/components.markdown)-based architecture applied across the engine in the form of :
  - ZilchComponents for game object behaviors 
  - ZilchFragment for fragment, vertex, and geometry shaders
  - ContentComponents for [Resources](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources.markdown) meta data 

 ## [Graphics](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics.markdown)
 - Fully modifiable, scripted rendering pipeline
  - With a [physically-based renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/physically_based_rendering.markdown) provided as the default renderer
 - Dedicated render thread

 ## [Physics](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics.markdown)
 - Custom-built, three-dimensional, constraint-based physics engine
 - Regions that can apply both pre-defined and user-defined [PhysicsEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
 - Robust, customizable [joint system](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/joints.markdown)

 ## [Audio](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio.markdown)
 - Scripted, [node-based](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode.markdown) DST system
 - 3D sound [positioning](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundemitter.markdown) and [attenuation](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown)

 ## [Zilch](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown)
 - High-level scripting and shader language


 # Learning the Zero Engine
Not all users have the same level of experience, with Zero Engine or game engines in general. The following guidelines and recommendations provide recommendations for any level of user with different types of background and experience to become productive in Zero.

 ## Novice Users
So you have never made a game or even programmed before. No problem! We have a sequence of [ tutorials ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials.markdown) and [ manual ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown) pages that will instruct you in the basics of both Zero and game programming in general. We suggest users of this level take the following steps to get started.

 ### New To Everything
 - The [standard tutorial sequence](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/tutorial_sequences.markdown) will get you up and interacting with the Editor in the shortest amount of time possible. It is an excellent place to start if you want to dive right in.
 - The ZeroManual contains a wealth of information If you find yourself curious about about a certain [major engine system](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown), [imported or generated resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources.markdown), or concept, such as  [components](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/components.markdown), [Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/scripting/eventsandconnections.markdown), or [archetypes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/archetypes.markdown).

 ### Some Prior Game Engine Experience
 - If you have some experience with another game engine, you may wish to create a new project and start playing around. The best way to learn is to do and experiment.
 - If you find yourself stuck or curious about a part of the engine you're unfamiliar with, check out the [ZeroManual](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown) for detailed coverage of the major systems,  individual elements, and concepts unique to the Zero Engine. 

Once you've mastered the basics taught in the Basics and Beginner  [tutorial_sequences](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/tutorial_sequences.markdown) and feel comfortable with the Editor UI and essential features, continue down to Intermediate Users.

 ## Intermediate Users
If you have some experience making games and programming, you will be able to pick things up fairly quickly.

 - Start with the [zilch_in_zero](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown). You will probably want to jump into scripting pretty quickly.
 - Read the [zeromanual](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown) starting with the [editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor.markdown), [architecture](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture.markdown), and [gameplay](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/gameplay.markdown) sections.
 - Browse [physics](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics.markdown), [editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor.markdown) and [audio](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio.markdown) sections for topics that are applicable to your project.
 - Read the remaining [zeromanual](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual.markdown) sections at your own pace.
 - If you are not fully confident in your ability to start operating in the engine, try out some [tutorials](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials.markdown).
 - Remember that you can always look things up in the [code_reference](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference.markdown)
 
