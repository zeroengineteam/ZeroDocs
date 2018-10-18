##General Principles
- Simplify
- Organized by what it does
- Embrace change
- Minimize dependencies
- Encapsulate what varies
- Readability is very important


### Core Engine Features


- Component base engine
- Game object management
- Serialization system
- Data driven object construction
- Reflection system for editing, scripting, and messaging
- Signal/Event system 
- Math library
- Platform independence
- Resource system
- Error handling


### Physical Code Structure


Engine is divided into separate libraries that are separate projects.
Libraries are organized in order from the most foundational (containers, math, etc.), to the engine (graphics, physics, etc.) to custom game code (game logic, scripts, etc.).
Each higher level layer only depends on more fundamental layers.



![LayeredArchitecture](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/3042.png)




### Fundamental Libraries

- Base libraries have no dependencies used by all other libraries. Essentially extensions to C++.
  - Common - Core C++ library including Containers, Assertion, and Memory management.
    - Custom container solution optimized for games
    - Custom assertion system ErrorIf(expr, "msg")
    - Memory support custom Pools, Heaps, and Stacks
  - Math - Floating point vector math library including matrices, vectors, and quaternions.


### General Libraries

- Used by all core systems and other tools.
  - Serialization - Library for saving and loading data in JSON, text, and binary.
  - Resource - Resource management and building.
  - MetaLibrary - Reflection system used for property binding (PropertyGrid) and Event Connections.


### Geometric Libraries

- Used by all core systems and other tools (such as exporters).
  - Intersection - Low level shape Intersection library used by physics primarily.
  - Broad Phase - Spatial partitioning library used by graphics, physics, and AI for scene management and frustum culling.


### Platform Libraries

- Used for platform independence. All platform dependent code is located here.
  - Platform - Contains platform dependent functions for file access and threading.
  - WindowsPlatform -  Right now the only working platform library. Others to be added in the future.


### Engine Libraries

- Base for communication between systems and defines core components shared between systems.
- Contains the core which updates all systems.
- Other Engine elements
  - Time management
  - Base Components
  - Connection System
  - Animation system


### System Libraries

- Core Systems - Run the major simulation systems of the game engine.
  - Graphics - Hardware accelerated graphics rendering.
  - Physics - Constraint based dynamics engine.
  - Sound- Hardware accelerated sound engine.


### Extensions

- Additional code that is not required for the core engine to run.
  - Widget - UI System used by editor.
  - Editor - Editor code and logic.
- On certain platforms, an extension may not be needed (the editor on a game console) or for a particular game (car physics in a puzzle game).
- Rather than bloat the core, these are optional.


## Game Object System

###Game Objects (Cogs)
- To create an object either use the ObjectSpace component or the Factory.
- Cogs must be created from archetypes which are strings in the form of "filename.data"
- Cogs must be created in a space.
  - Except for a space object itself


### Components

- The game object composition class (Cog) is a collection of components provided by the different systems.
- Every component class inherits from a base component class and has reference/pointer to its owning composition.
- When the game object composition is destroyed, it destroys all of its components.


### Creating A Cog

```
  Archetype* shipArchetype = ArchetypeManager::Find("Ship");
  Cog* cog = space->Create(shipArchetype)
```


### 'has' Operator

- Used to get components from compositions by type name.
- It is type safe and will return NULL or a valid component.

```
Model* model = cog->has(Model);
if(model)
{
  model->SetColor(Vec4(0,1,0,1));
}
```


### Handles / CogId

- The engine uses handles to safely refer to Cogs.
- CogIds do not keep the object alive.
- CogIds must be checked for NULL.
- Once a CogId is checked it is safe to use that object for the rest of the frame.

```
void SomeFunction(CogId target)
{
  if(Cog* cog = target)
  {
    if(Transform* transform = cog->has(Transform))
    {
      transform->SetTranslation(Vec3(0,10,0));
    }
  }
}
```
also works on CogIds

```
void SomeFunction(CogId target)
{
  if(Transform* transform = target.has(Transform))
  {
    transform->SetTranslation(Vec3(0,10,0));
  }
}
```


## Meta Data

- Engine has a C++ Meta Object Reflection System.
- A Meta Object provides a map of member functions, member properties, and member objects.
- Used for property viewing/editing, reflection, and many editor features.
- Used for scripting engine to bind C++ functions.


### Binding

- Binding is done by a static member function called InitializeMeta() on a class.
- The function is called when the class is registered or when InitializeMetaOfType is called.
- All the binding functions are Macros to make binding easy and compact.


### Meta Data Contents

- Properties
  - A Getter and Setter function for field or data member.
  - From the outside just a data member but setting may have side effects.
  - Used for editing on the property grid.
  - Example Position, HP, Color, etc.
- Methods
  - Member functions on objects.
  - Used for event connections, scripting, and simple commands.
  - Example OpenDoor, PlayAnimation, Spawn, Unlock etc.
- Dependencies
  - For components, what other components MUST be present for a component to function.
  - Used to provide safe component addition and removal in the editor.
  - Also, documents relationships between components.
- Events
  - A list of events that can be dispatched on this object.
  - Used by the editor to form connections.


### Component Interfaces

- Multiple Components may provide the same interface functionality and it does not make sense to have more that one. 
- Examples: Collider, Joints, etc
- Editor enforces only one component that has a particular interface. For example only one collider component (like BoxColllider) can be present.

```
void ComponentExample::InitializeMeta(MetaClass* meta)
{
  // Must have transform
  BindDependency(Transform); 
  // Bind shield strength member variable
  BindMemberProperty(mShieldStrength);
  // Bind the member function ActivateShield()
  BindMethod(ActivateShield);
  // This object can send the event ShieldDown
  BindEvent(ShieldDown, GameEvent);
  // This class implements the ShieldProvider interface
  BindInterface(ShieldProvider);
}
```

### Bind Member vs Property

- BindMemberProperty
  - Binds any member variable of a class.
  - Used for quick binding (no get and set function).
- BindGetSetProperty
  - Binds getter and setter function to act as a property.
  - Allows programmable behavior (for example fetching a resource or updating position)
  - Expects the getter and setter to be named Get'PropertyName' and Set'PropertyName'


### Other Special Properties

- Enumerations
  - Enums automatically make a pull down on a the property grid.
  - Must be declared with DeclareEnum macro.
- Range Properties
  - Displays a slider on the property grid.
- Resource Properties
  - Automatically uses the resource system to display a list of resources.


## Serialization

- Converting an object to and from a file, buffer, network, server, etc.
- Normally moving from a runtime object to a file or buffer and back.
- AKA saving and loading.
- Save and load levels, copy and paste, all of data file loading, including many resources.
- If data needs to be loaded from a file it goes through the serialization.



![Serialization](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/3044.png)



## Example Serialization Code


```
class ComponentExample
{
public:
  float mHitPoints;
  Vec3 mDirection;
};

void ComponentExample::Serialize(Serializer& stream)
{
  // Expands to stream.SerializeFieldDefault("mHitPoints", mHitPoints, 100.0f)
  // and we implicitly remove the 'm' in the data file
  SerializeNameDefault(mHitPoints, 100.0f);
  SerializeNameDefault(mDirection, Vec3::cXAxis);
}
```


## Example Serialization Result

```
ComponentExample = 
{
  float HitPoints = 20,
  vec3 Direction = [1,0,0]
}
```


## Data File Types

- Text
  - Human readable basic JSON like format.
  - You can view an object Text by copying it to the clipboard.
- Binary
  - Optimized binary format, compact and fast to load used for caching.


### Splitting Saving and Loading

- The save function handles both saving and loading to reduce the amount of code.
- Splitting saving and loading can be done based on the serialization direction.
- Versioning is also handled by the system for text files.


### Object Serialization Phases

 - Construct the object
  - Constructed - Object has been built from the factory but is not active.
 - Serialization and data setting
  - The object is serialized and then data attributes are adjusted.
 - Initialize the object
  - Object really comes into existence using all the serialized data.
 - Object is destroyed


### Special Serialization


- To be serialized, Enums must be declared with DeclareEnum.
- Resources also have specialized serialization.


### Serialization of Cogs


- When a cog is serialized, it uses the data file to find the components it needs.
- All components are registered to the factory.
- The factory looks up components by string, constructs them, and then serializes them.
- When all components are created and serialized the composition is initialized. 


## Initialization

###Component Initialization
- Do not do anything in a component constructor except initialize values.
- All the real work is done in Initialize.
  - Get pointers to other components
- Add component to various system
- Watch out for order of initialization Dependant components are initialized first.


### Example Initialization Code

```
void GraphicsComponent::Initialize(CogInitializer& init)
{
  // Getting other components
  mTransform = GetOwner()->has(Transform);

  // Adding to the graphics space (or maybe system)
  GraphicsSpace* graphics = GetSpace()->has(GraphicsSpace);
  graphics->AddModel(this);
};
```


## Events

- Events are used to communicate between Systems, Game Objects, and Spaces.
- This is a listener pattern similar to signal/slots, flash events, or delegates from C#.
- An object *connects* to a target object, then listens for a particular event to be dispatched
  - Calls the specified function on listening object


### Connect

```
  Connect(targetObject, Events::EventName, receivingObject, &ObjectType::FuncName);
```
- For example, the object that is involved in a collision event will have a function called when the event occurs and are constant strings.

  - Usually this is the class doing the connection is a member function pointer othat will be called when the event fires.


### Connecting Example Code

```
void GraphicsComponent::Initialize(CogInitializer& init)
{
  // ConnectToThis expands to Connect(target, event, this, &classname::function)
  
  // Connect to our own Cog
  ConnectToThis(GetOwner(), Events::VisibilityChanged, OnVisibilityChanged);

  // We want to be updated every frame (regardless of being paused)...
  ConnectToThis(GetSpace(), Events::FrameUpdate, OnFrameUpdate);       
}
```


### Declaring Events

- Creates a constant string used to hook up events.
- Prevents allocation of multiple string objects.
- Makes it easy to hook up events.


### Event Objects

- When an event occurs an event object is sent.
- All event objects inherit from the base Event object.
- Many events use the same event object
  - For example most mouse events (Move, Click, etc) send the event object MouseEvent
- This makes it easy to refactor and add new data without changing a lot of code.


### Connection

- Connections are cleaned up automatically when either object destroyed.


### Example Event Connections

```
void ComponentExample::Initialize(CogInitializer& init)
{
  ConnectToSelf(GetOwner(), Events::CollisionStarted, OnCollisionStarted);
}

void ComponentExample::OnCollisionStarted(CollsionEvent* event)
{
  event->OtherObject->Destroy();
}
```

### Container Library

- A game oriented replacement for STL.
- Most of the same containers.
- Mostly the same interface.
- Several key game oriented features.


### C++ stl Equivalents

- std::vector -> Array
- std::unordered_map -> HashMap
- std::unordered_set -> HashSet
- **No std::map** (use HashMap)
- **No std::list** (use InList)


### Intrusively Linked List

- Intrusive containers are useful for efficiency
- Most heavily used container besides Array.
- The next and previous pointers are stored on the object itself.


### Ranges

- Containers use ranges in place of iterators for most moving in a container.
- Ranges are more secure and easier to work with than iterators.

```
int Sum(Array<int>& values)
{
  int total = 0;
  for(Array<int>::range r = values.all(); !r.empty(); r.popFront())
  {
    total += r.front();
  }
  return total;
}
```
```
int Sum(Array<int>& values)
{
  int total = 0;
  forRange(int a, values.all())
  {
    total += a;
  }
  return total;
}
```


### String vs std::string

- std::string suffers from trying to be everything to everyone and is often large
- Greatly improves hashing, indexing, equality, and string passing
- Game engines mostly just pass strings around and index with them so immutable strings are ideal


### Working with Strings

- Strings are immutable so they can not be modified so how do you change them?
- Assign a new string!
- For large amount of string appending use StringBuilder 


### StringRange

- Essentially replace const char*
- Internally two pointers to begin and end.
- Safer faster and easier to work with than null terminated string.
- Contents are always immutable.
- C style strings should effectively never be used.


### Memory and Allocations

- STL allocators are very complicated to use.
- Engine containers use a simplified version of allocators that is faster, more flexible, and easier to use.
- The allocator itself is not templated and can be virtual.
- Each container has a instance of an allocator.
- These work with the memory system to track all allocations.


### Benefits

- Containers optimized for POD types.
- Designed to do minimal code generation
- Shallow function calls to increase performance
- Easy to read and understand (stl tends to be obfuscated)
- Intrusive containers
- Supports aligned data types
- Supports object sharing and memory pooling to prevent fragmentation
- Controled memory useage / containers do not allocate memory before it is needed.


## Include Structure

- Engine uses pragma once instead of inclusion guards (clearer, faster, and support by all needed compilers)
- All include statements start from one of the roots (Systems or Utility)
- Examples:
 - "Graphics/Model.hpp"
 - "Containers/Array.hpp"
- It works on all platforms
- Engine used precompiled headers for all projects.


## Asserts

- Engine uses a custom assert system
- Does not use the usual assert syntax
- Primary function is ErrorIf(expression)
- Also has *printf* functionality
- ErrorIf(pointer == NULL, "Could not find object named %s", objectName.c_str())
- Exceptions are not used
 
  
  
  
  
  
  
  

 