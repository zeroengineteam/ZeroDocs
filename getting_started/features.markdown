# Ten Exciting Features of the Zero Engine (and also Spaces)

## Events

Zero Engine’s Event system takes component-based design to new levels of freedom and flexibility. A Zero Engine Event mimics its real-world counterpart: a situation that arises. How your game handles that situation is up to you. When your hero takes damage, the camera following her can shake. When a cannonball reaches the apex of its flight, an audio filter can be applied to the level’s music. Every game object is a potential event dispatcher, and every object’s events are up for grabs. When you work with events from the beginning of a project, you allow yourself greater freedom to rapidly explore new features and ideas with minimal refactoring of your existing code.

## Nested Archetypes

An archetype defines a game object, its child objects, and even other nested archetypes within the hierarchy. Need to make changes to an Archetype that is nested under multiple of other Archetypes? We've got you covered. Every Archetype will automatically receive updates made to nested Archetypes. Did all those Archetypes have local modifications made to the nested one? We've still got you covered. Zero Engine preserves local modifications when updates are made to an Archetype.

## Zilch

Zilch is a high-level programming language developed by us to solve some of the most interesting problems in game development. Use Zilch to program and customize game scripts, editor tools and commands, and even your shaders. All of that, done in an integrated text editor equipped with full code completion and inline tooltips from documentation. Zilch features extremely fast compilation and patching/hot loading for live game editing.

## C++ Plugins

Scripts are awesome, but at the end of the day they can't do everything that life has to offer. Whether it's a library that you want to use or you need to do some heavy lifting for performance reasons, C++ can always get the job done. With a C++ plugin you have all the power you need, wrapped up and ready to use in your game. There’s no complicated setup, just create a new plugin resource and it will make you a Visual Studio solution, pre-hooked with a new component. Changes to your plugin are automatically detected by Zero Engine, and your project updates itself on the spot.

## Lightweight Game Objects

Zero Engine’s game objects are lightweight and versatile. We call them cogs because they’re 'Game Object Compositions' (and “gocs” doesn’t sound as cool). Cogs can house as many components and child objects as needed, and the engine is incredibly good at making and destroying them, so you never have to worry about object pooling.

## Shader Compositing

Zero Engine's Materials are a component based way to write shaders. Write individual shader fragments to encapsulate a desired behavior, and add the fragments you want to your Materials, just like components, to create the desired effects. The shader compositor does all the work of putting the components together to create a complete shader program for graphics hardware. It also controls the flow of inputs and outputs between fragments, so that a single fragment can modify data, like UV coordinates, before it is used as input to a following fragment.

## Scriptable Rendering Pipeline

We're in the business of rapid iteration, and the rendering pipeline is no exception. Zero Engine offers unparalleled control over the aesthetics of your game with the ability for scripts to define a series of tasks for the renderer. Written in script, your rendering pipeline becomes anything you can imagine, make your pipeline change dynamically with a simple condition, or even in response to an Event. Add any rendering technique to your game, including the ones that haven't been invented yet. But there’s no need start from scratch: Zero Engine comes pre-loaded with all the scripts and shaders needed for a modern physically based rendering pipeline. If that’s what you’re looking for, you’re done. If you want more, you can use it as a starting point for customization.

## Scriptable Sound Nodes

Zero Engine features a powerful custom audio system. At its core is the sound node graph, a flexible, fully scriptable structure that controls the flow of audio through your game. Sound nodes can play or generate audio, apply effects, control parameters, and more, and they can be added, removed, and swapped at any time. When the sound node graph is used together with Zero Engine’s built-in event system, it’s easy to apply DSP effects to just the right sounds, just when you need them.

## In-House Physics

Like most things in the Zero Engine, our physics system is developed by us. That may seem like an unnecessary amount of work, but we want features that pair well with the design and vision for Zero Engine as a whole and we don't want to be held back. Zero Engine’s physics system includes features like collision groups that allow detection without resolution, regions that can apply force effects, and even scriptable joint definitions that run through our constraint solver.

## One-Click Network Replication

Networking is easy! ... Okay we're kidding, but the road to easier networking is full of innovation, and what's easier than one mouse click? Zero Engine continues to use component based design to every advantage we can come up with. Just add the NetObject component and now any property from your object can be replicated over the network with a single click of a button in the UI. Start from our networked project template to get a head start with some of the harder stuff.

## Spaces

The concept of the space is quite unique: a space is a collection of game objects that interact normally with one another, but not with objects in other spaces. Physics is simulated in each space separately, so objects in two spaces running simultaneously could experience completely different gravity, force effects, and collision rules. Separate spaces can be paused independently, so your game can be frozen in one space while the animations keep going in another, such as in a menu. The output of cameras from separate spaces can be overlaid, split screened, or embedded in objects in a level, so an in-world TV screen could be used to play a game-within-a-game. A space can even be created with no cameras in it at all, serving instead as a storage repository for data that should persist between levels or even networked game sessions.
