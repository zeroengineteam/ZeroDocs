```
  digraph
  {
    node [shape=rectangle, fontsize=10, height=0, fontname=Verdana];
    edge [fontsize=10, fontname=Verdana];

    "Engine" -> "Systems" [label="owns"];
    
    "Systems" -> "ShellSystem";
    "Systems" -> "TimeSystem";
    "Systems" -> "PhysicsSystem";
    "Systems" -> "GraphicsSystem...";
    
    "Engine" -> "Game Sessions" [label="owns"];
    
    "Game Sessions" -> "Spaces" [label="owns"];
    
    "Spaces" -> "Cogs" [label="owns"];
    "Spaces" -> "LevelSettings" [label="own"];
  
    "Game Sessions" -> "Editor GameSession";
    "Game Sessions" -> "Game1 GameSession...";
    
    "Editor" -> "Editor GameSession" [label="uses"];
    "Editor GameSession" -> "Editor Spaces" [label="uses"];
    "Editor Spaces" -> "Tools (Cogs)" [label="uses"];
    "Editor Spaces" -> "Commands (Cogs)" [label="uses"];
  }
```

Philosophy
 ### 
The driving philosophy behind Zero has generally been to re-use as much code as possible in different locations. This is the reason we use component based design. Its much easier to share code by adding components then it is in an inheritance model. Zero also maintains its WYSIWYG style by reusing code between the editor and game-play. All components that we write in C++ generally have to acknowledge that they can be used in both editor and game, which is an advantage since they can display the best data to the editor (such as a Microphone component debug drawing its virtual ears). Because it is difficult to trust the user to write code that works perfectly in both editor and game, by default we 'proxy' their Zilch components in the editor. The proxy is basically a fake object that looks exactly like their object, but does not run their code (all the same properties). We do expose the ability for users to make their scripts run in editor if they would like.

Recent Refactors
---
One major example of refactors we've done in the name of code reuse: Tools. The tools in Zero (Translation, Rotation, TileMap, etc) used to all derive from a base class called Tool. Starting out, we originally had a bunch of virtual functions you would override for MouseMove/Down/Up over the main editor's Viewport. This worked ok, but after we started using events everywhere (for mouse input, keyboard input, etc) we eventually refactored these tool virtual to be events, getting rid of the virtuals on the base class and reusing events we already had. From there we ran into the issue that users wanted to write their own tools. We could expose the base class Tool to script (such as a ZilchTool) but we realized that there is a lot of functionality the user wants. They want to be able to give the tool an icon, define properties on the tool, live edit the tool's script while the engine is running, proxy the tools if there is a Zilch compile error upon loading, etc. We realized that the Cog (our game object) already supported all this functionality, so why not just make the tool into an Archetype, effectively removing the Tool base class. We then realized that the user could add components to tools which makes them incredibly extensible (they can now send events, lookup other components, etc). Moreover, working with Cogs is a paradigm users are already used to, so now there's even less to teach them.

Useful Libraries
---
Behind the scenes at the core of Zero is the Meta system, which exposes methods and members of C++ objects to both the GUI and Zilch. To maximise code reuse, we rely heavily upon the property grid GUI. The property grid automatically generates GUI based on the members of an object (either from C++ or from Zilch). The property grid is also built to handle component based design (adding and removing components at its core). By using the property grid, users don't have to create custom GUIs for every type of object/component/tool they add to the engine. Having said that, sometimes it is advantageous to write custom UI, such as in the case of the Animator tool which requires time-lines and key-frames. With the Meta system, we can query for type information such as how many members a type has and what their names are, how many methods and what parameters they take, etc.

We also have a serialization system that serializes out to our own format (though it is somewhat similar to JSON). We maximise code reuse by using bi-directional serialization, which means we use a single function to both save and load an object, instead of writing two separate functions. We also support serialization from Meta, which is the quickest way to save and load all of an objects properties. In the future, we may switch to serialization being entirely from Meta, because it would simplify some of our paths and reuse more code.

Almost everything in Zero is written from scratch (with the exceptions of a few minor libraries such as libpng, zlib, freetype, etc). These libraries dive deeply into the specifies of file formats and unit test them very well, so we opted to use these libraries where they make sense. Aside from that, everything including the physics, graphics, scripting, networking, and even eventually the sound engine will be written by our team.

Engine Classes
 ### 

Engine
---
The Engine class is created once (allocated and stored into gEngine). Calling Run on the engine starts the main loop, and it will continue running until Terminate is called. The Engine invokes the Update function every frame, which walks through all the Systems that were added to the engine in the WinMain/Startup function. Many of our objects in Zero use delayed destruction (such as Cog) which means when we call Destroy on them, they are marked for deletion and added to a list to be deleted later. The Engine deletes these objects upon its Update every frame. The Engine is also responsible for pumping events that come from other threads in its Update.

System
---
A System is effectively a component that gets added to the Engine. Examples include the PhysicsEngine, SoundSystem, etc. The SoundSystem is a particularly good example of a system because it has one time initialization and destruction logic, such as starting up the mixing thread. Moreover, the SoundSystem must be updated every frame to receive threaded notifications from the mix sound thread. Some Systems, such as the TimeSystem and the PhysicsEngine mostly manage updating space components such as the TimeSpace and PhysicsSpace. By updating them when we update each system, we ensure that all spaces have their LogicUpdate run, then all spaces have their physics updated. Note that order of the Systems is very important to reduce input lag.

Cog
---
The Cog is our base composition class to which components can be added. Space and GameSession both inherit from Cog. Cogs are typically created via the Factory (gFactory) which handles looking up types by name and then creating them (including components). Cogs use delayed destruction, which means they don't instantly get deleted upon calling Destroy, but rather get destroyed at the beginning of the next frame.

Component
---
Component is our base class for all components. Cog contains an ArrayMap of components (mapped by type id for quick typed lookup). We generally only allow there to be one component of a particular type per Cog. Components are mostly WYSIWYG in the editor, in that the actual components we code up in C++ are exactly the same ones running in the editor. The only major difference is that the editor is generally paused which stops physics and other time based systems from running.

Proxy Components
---
Proxy components are a special class of components that pretend to look like another component by duplicating a component's meta. The proxy component is a property bag (map of strings to variants) and can store anything. Proxy components are useful because they don't run any code in the editor. All script components are proxied when they are added in the editor, but in the actual game they are substituted for the actual component.

Engine Components
---
- Requires documentation
  - Transform
  - Object Link
  - Area

Game Session
---
The GameSession manages all created Spaces, and is effectively an instance of a running 'game'. Every time you press F5 in the editor or run a standalone exported project, a GameSession is created. If you press Ctrl+F5, multiple GameSessions will be ran at the same time, which is useful for networking tests. GameSession inherits from Cog and can therefore have components (including ZilchScripts) attached to it. The GameSession gets events sent on it, such as GameStarted where you can create spaces and load levels. The editor has a GameSession that you can edit and add components to (which will be used in the game). You can also attach [RunInEditor] scripts to the editor GameSession. The GameSession will destroy all child Spaces when it is destroyed.

Space
---
Spaces are one of the main features that sets Zero apart from other engines. A Space contains a collection of Cogs (game objects). Each Space is independent of another Space. For example, you can have a physics object at (0,0,0) in one space, and a physics object at (0,0,0) in another space and the two objects will not interact or collide. We've found that Spaces are a great way to do UI, because you can run a separate space from your game that has UI objects in it. In many other game engines, the UI is either something entirely special, or you have to parent objects to your Camera which is cumbersome when you want to change cameras.

Spaces can be given a name and are always created through the GameSession (which owns the Spaces). Named spaces can be found via the GameSession's FindSpaceByName. Because Space also inherits from Cog, you can add components and scripts to it. Although you can just create objects in a Space, the primary usage case is calling LoadLevel, which loads a collection of objects into the Space. The first time LoadLevel is called it is instantaneous (right after the call, all the objects are created). The subsequent times LoadLevel is called on the same space, it will be delayed by one frame. This is to avoid the issue of two objects existing at the same time with the same names and so on due to delayed destruction. Users will typically either listen to the LoadLevel event to perform level logic, or they will always create new spaces and call LoadLevel only on new spaces to ensure it is always instantaneous.

Level Settings
---
The LevelSettings object is actually part of the Level resource (just another object) but is worth mentioning in the context of the Space. The LevelSettings should always be the first Cog in the Space's list, and is therefore guaranteed to be initialized before any other object. Moreover, many built in components use the LevelSettings object as a way to define global effects for the entire level. For example, I can add a ForceEffect to the LevelSettings and then all objects in the current level will get that force applied. This isn't built in or special behavior of the LevelSettings, but rather the PhysicsEngine looks for any force effects first on the Cogs, then on the LevelSettings, and then on the Space. This is a common pattern. LevelSettings is also very core to writing user logic, so we put that property on both Space and Cog. You can directly access LevelSettings by doing 'this.LevelSettings' instead of trying to find it by name.

Factory
---
The factory (Z::gFactory) is responsible for constructing a type from a serialzied name such as a Cog, Space, or any components like Transform. Currently, the factory mostly only handles Cog related types, however our Meta can also be used as a factory.


CogInitializer
---
The CogInitializer is a type passed to each cog that is being initialized. When we create Cogs, we could be creating multiple, ie loading Cogs from a level, loading an Archetype which has a hierarchy with children, etc. Multiple Cogs loaded at the same time is known as a serialization context (we commonly refer to it as 'all objects within the context'). The CogInitializer stores a bunch of data that is useful to each cog being created, for example the parent GameSession or Space it is being created within. We also send the AllObjectsInitialized event on the CogInitializer once the entire initialization phase is completed for all objects within the context.

Handles
---
Cogs use a safe handle system that allows us to look up a cog by id and version: a pattern also called 'slot map'. The CogId class encompasses the id and version (two integers). CogId can implicitly convert to a Cog* and will be null if the object no longer exists. We originally used to directly store Cog* in many places, but we found that it was almost always a bad idea to assume the object still existed (dangling pointers). The user can delete objects, spaces can be unloaded, actions can delete objects, etc. We now almost always store references to objects in C++ as CogIds. We do work with Cog* on the stack because we know that with delayed destruction, the objects WILL NOT be deleted until the beginning of the next frame. Moreover, in script all references to Cogs are actually CogIds just to keep scripts safe. As a side note, whenever we pass around MetaHandles to Cogs, we're essentially just stuffing a CogId into the MetaHandleData.

Archetype
---
Archetypes are a data resource that stores a serialized Cog. Archetypes can be referenced within a Level and can also be created and loaded into a space. The advantage of Archetypes is that they allow instancing the same object in multiple places (sharing) and when the Archetype definition is changed in editor, all instances of that Archetype change. Archetypes are stored as text serialization, however we cache them using binary serialization so that subsequent creation of the same Archetype is very fast. This cache must be dumped any time a change to script is made (such as the order of members) because the binary serialization is linear: members are directly read in the order they are saved in. When an Archetype is uploaded in a Level in the editor, we run special code to update all live instances of that Archetype in the same level. When an Archetype is modified it gets a special flag that says it is locally modified within that level, meaning the object is basically copied into the level and is not instanced.

Hierarchy
---
Cog Hierarchies allow for any Cogs to be parented to other Cogs. When a parent Cog is destroyed, all of its children are destroyed, and so on. It is up to the components to give meaning to parenting. For example, Transform knows that when it gets childed to another Transform, it will act as a relative object and concatenate matricies. Physics Colliders and RigidBodies also have special behavior for childed objects, such as multiple collision volumes for a single object. Hierarchy uses an intrusive list to maintain the list of children and the hierarchy link is on the Cog itself.

Initialization Order of Cogs
---
Related to hierarchies is the initialization order of Cogs. Cogs are initialized from first to last object in the object view, and from parent to child. This is why LevelSettings is the first object to be initialized. The order of initialization is important because scripts may rely on this order. Moreover, we found that if script components were initialized in the same phase as C++ components, then they were often able to access data before it was fully initialized and crash the engine. This lead to separating script initialize into its own phase. Though it sounds obnoxious, we actually have effectively 4 phases of initialization. The first is calling Initialize on every component in C++. In the Initialize phase, we can only assume that other components that are above ours have been Initialized. Specifically we can rely on our component's dependencies being initialized. Then we invoke OnAllObjectsCreated on every C++ component, a phase where we know all components have been Initialized. Note that we must run ALL Initializes first and then ALL OnAllObjectsCreated in order for them to actually be correct. After that, we run ScriptInitialize on all script components, therefore we know all C++ components are fully initialized. Lastly, we send the AllObjectsInitialized event on CogInitializer which anyone can listen to.

CogPath
---
In the beginning of Zero we needed a way to refer to other objects by id, and this id would have to persist through serialization (data saved to disk). This was useful if we wanted one object to point at another, eg a following script, and then we could save that link in the level. This problem is easily solvable if both objects you are linking are contained within the same file (two objects in a level, two objects in a single archetype, etc). However, once the objects were split apart into different files the problem becomes nearly impossible to solve properly. This case was especially common when a user would make a Zombie script and then use the Cog id's to point at the Player. As soon as the Zombie was uploaded to its own archetype, it would lose its own reference to the Player because the Zombie file by itself could no longer properly refer to the Player saved in the level. Many other popular editors exhibit this same behavior, but we deemed it undesirable. CogPaths were a partial solution to this problem. By using the names of objects and the hierarchy order, we gave the users a unique way to identify which object they were referring to. CogPaths also combine using the id so that they can best try to save, load, and continue pointing at the same object you originally picked without losing a reference. CogPaths use string lookups to find children Cogs, and special operators to find parents, children by index, children by archetype name, etc. The syntax of CogPaths also allows the user to find objects in different named spaces, which is very useful for UI.

Events
---
Zero uses an event system at its core which allows any class to send and receive events. An event is basically just a callback (function pointer) plus an event data structure with all the relevant information to the event that occurred. For example, you can listen for the KeyDown event on the global Keyboard object, which tells you what key was pressed, as well as other helpful features such as if Ctrl, Shift, or Alt were pressed too. The event system is critical to the performance of Zero because it discourages writing poll-based logic. Having a bunch of objects that update every frame and check to see if a key gets pressed is generally much less efficient than having a single object getting updated (the Keyboard) that then calls into everyone when a key gets pressed. Moreover, events allow for some level of dynamic dispatch. You can send an event to anyone and they may or may not handle it (think of it like a message). I can do a ray-cast and send the Open event to the first object I hit, which may do nothing, or it may open a door or a chest. Events can also be forwarded or bubbled up / down a hierarchy, which is very useful for UI. The common class that everyone inherits from to automatically get event handling is the EventObject class.

Engine Events
---
- Requires documentation

Systems
 ### 
There are many different Systems that we add to the engine. One of the more important ones it the TimeSystem. The TimeSystem has a intrusive linked list of all TimeSpace components (which are components that get added to each Space). When the TimeSystem updates, we compute the amount of time passed since the last frame, and then we walk through and update each TimeSpace. The TimeSpace update will dispatch critical events such as LogicUpdate, FrameUpdate, etc. Many different components (including user scripts) rely on LogicUpdate being sent on the space.

Actions
---
- Requires documentation

Job System
---
- Requires documentation

Project
---
- Requires documentation

Object Store
---
- Requires documentation

Resources
---
- Requires documentation

Engine Resources
---
- Requires documentation
  - Archetype
  - Level
  - TextResource
  - SampleCurve
  - Paths
  - ResourceTable
  - DocumentResource

Animations
---
- Requires documentation

Animation
---
- Property Track
- Event Track

Rich Animation
---
- See Editor Rich Animation

Animation Editor
---
- See Editor Section

Animation Graph
---

Events:

Animation Nodes:

- Pose Node
- Basic Node
- Direct Blend Node
- Cross Blend Node
- Selective Node
- Chain Node
- N-blend Node

Graph Visualization
---

Simple Animation
---
- Requires documentation

Input / Shell System
---
- Requires documentation

Tweakables
---
- Requires documentation
 
  
  
  
  
  
  
  

 