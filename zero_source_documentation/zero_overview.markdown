- Engine is divided into Systems that are updated every frame.
- Game objects, called Cogs, are a composition of Components provided by the systems.
- Game objects are created from data files by the Factory and placed in Spaces (aka worlds).
- Objects communicate through Events and through direct access to other objects.


## Component Based Engine


- The game object composition class (Cog) is a collection of components provided by the different systems.
- The components provide units of functionality for the composition.
- A component can be data, behavior, and/or a link to a system.
- When the game object composition is destroyed, it destroys all of its components.

.. image:: Zero/ComponentBasedEngine.png


## Dynamic Composition


- All compositions are composed dynamically
- No "Main Camera", "Floor", or "Ball" class is defined in C++.
- Compositions come from data files
- The files "MainCamera.data", "Floor.data", and "Ball.data" define which components the composition uses and the data those components need.
- So objects can be built at runtime by designers!


### Example Compositions




![ExampleCompositions](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/3040.png)




### Sample Cog Data File


```
  Cog = 
  {
    Transform =
    {
      float[] Translation = [ 8.5, 10, 1 ] ,
      float[] Scale = [ 1, 1, 1 ] ,
      float[] Rotation = [ 0, 0, 0.0, 1 ] , 
    },

    Model =
    {
      string MaterialName = "Caution" ,
      string MeshName = "Cube" ,
    },
  }
```


### Core Engine Components


- Transform - Position, Rotation, and Scale.
- Timeline - Animation of properties and events.
- Hierarchy - Component used to place objects in directed acyclic graphs (trees).


### Common System Components


- Defined by different systems (PhysicsSystem, GraphicsSystem, etc)
- Collider - Defines the shape of the object and provides collision with other objects.
- Rigid Body - Allows the object to move around and rotate in physics.
- Model - Draws a 3d mesh at the transforms location.


### Component Dependencies


- Components can depend on other components (or interfaces) in the composition.
- Components register their dependencies and look up their dependencies when they are created.
- The editor enforces the dependencies to prevent the creation of bad compositions.


### Example Dependencies


- Many components (model, collider, camera, etc.) depend on the Transform component for position, rotation, and scale.
- The Camera Controller depends on the Camera component.
- The Light Cookie component (used to apply a light stencil) depends on the Light component.


### Spaces


- The engine can support multiple "worlds" or Spaces.
- Spaces are game objects compositions with components corresponding to the different systems (PhysicsSpace, GraphicsSpace, SoundSpace).
- Used by the editor and for level chunks.


### Spaces in Practice


- Usually two spaces "UI" and "EditorWorld". 
- Sometimes a "PreviewSpace" is used to preview game objects.
- When the game is played from the editor it creates a separate space so the "EditorWorld" is not affected.
- There is no global world object. All game objects have a reference/pointer back to their current space.


### Data Systems and Archetypes


- Game objects are created from data files by the Factory, which uses the serialization system to read the data.
- Game object data files are Archetypes (aka prefabs or templates).
- Archetypes are normally created and modified in the editor.
- This is how designers create game objects.


### Archetypes in the Editor


- An individual game object is created in the editor by selecting an archetype and placing it.
- If that archetype is modified, any placed game object with that archetype will be modified when the changed archetype is uploaded.
- If desired, the archetype link to a specific game object can be broken, so that changes to the archetype will not affect that object.


## Events


- Events are used to communicate between Systems, Game Objects, and Spaces.
- This is a listener pattern (similar to signal/slots, flash events, or delegates from C#).
- An object *connects* to a target object, then listens for a particular event to be dispatched (which will call the specified function on listening object).


### Elements of Events


- EventId - The event Id is a string that identifies the event.
- Event Object - The event class is the data sent in the event. The same event class may be used for multiple events.
- The Dispatcher - Object the event occurred on.
- The Listener - Object that listens for the event.
- Connection - Contains references to both objects and the bound function to call on the listener. 
- An object can connect to itself.


### Event Bubbling


- When an event occurs it can Bubble to classes above it in the hierarchy. 
- This is very important for UI objects.
- Example: A hand bone on a character gets hit. The event is bubbled up to the root bone and then to the character game object, where an AI component is listening (and responds by deciding to run away).


### Event Examples


- When a button is pressed it dispatches a "Pressed" event of type MouseEvent. ObjectB (the menu) receives the event and opens a window.
- When ObjectA collides it sends out a "ContactStarted" event of type CollisionEvent. ObjectB receives the event and plays a sound at the collision's location.


## Resources


- Shared objects that are used by game objects.
- Most have to be processed by the resource system, and some are just simple data files.
- Examples: Materials, Meshes, Textures, Sounds, and Archetypes.
- A Resource is requested from the ResourceSystem through its name (in the editor) or through its ResourceId (in code).


### Resource Libraries


- A collection of resources organized however users of the editor wish.
- Libraries are stored in a shared folder on a computer that the engine is installed on and can be shared by different projects.
- Users of the editor decide which libraries they need for their project, while the editor handles loading the resources in each library automatically.


### Resource Library Types


- SourceLibrary - the raw unprocessed version of the resources (.psd, .maya, .fbx, .wav, etc)
- ProcessedLibrary - the processed version of the resources ready to be loaded. These are different for different platforms.


### Resource Packages


- Each Space automatically generates a ResourcePackage that includes all the Resources it uses, regardless of which libraries those resources are in.
- A given level could consist of multiple Spaces, each with its own Resource Package (useful for streaming).
- Resources are intelligently cached by the engine, so you do not have to worry about duplicating resources in different packages.


### Custom Resource Packages


- Custom Resource Packages can be created in the editor, where exact resources from any library can be specified. 
- This is normally done when game objects or resources are dynamically created in C++ code (which means the automatically generated resource packages don't know about them).

 
  
  
  
  
  
  
  

 