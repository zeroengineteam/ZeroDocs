Custom Event Names
------------------
We start by making a externed string in our header file:
```
namespace Zero
{
  namespace Events
  {
    DeclareEvent(FlagCaptured);
  }
}
```
And within the cpp file we must define the string:

```
namespace Zero
{
  namespace Events
  {
    DefineEvent(FlagCaptured);
  }
}
```

By placing the event within the `Events` namespace, we can conveniently access any events name via `Events::FlagCaptured`.

Custom Event Types
------------------
To create an event type that we can send (*this is not required*) we can make a new class that inherits from `Event`:

```
class FlagEvent : public Event
{
public:
  ZeroDeclareType(FlagEvent);
  static void InitializeMeta(MetaType* meta);
  // Any data you wish to put here
};
```
Notice that this class uses the `ZeroDeclareType` macro. This means that it is important that we use the counterpart `ZeroDefineType` within the cpp, and that we must absolutely be sure to call `BindBase` on Event as well as `InitializeMetaOfType(FlagEvent)` elsewhere in the initialization portion of our code. See [meta_binding](https://github.com/zeroengineteam/ZeroDocs/zero_source_documentation/meta_binding.markdown) for more details.

```
ZeroDefineType(FlagEvent);

void FlagEvent::InitializeMeta(MetaType* meta)
{
  BindBase(Event);
  // Any members we want bound to script
}
```

Sending / Receiving Events
--------------------------
Sending an event is generally:

```
FlagEvent toSend;
  target->GetDispatcher()->Dispatch(Events::FlagCaptured, &toSend);
```

The `target` in this case is whoever we want to send the event on.

In some places we have helper functions like `DispatchEvent` to make this more convenient (such as on component):

```
FlagEvent toSend;
DispatchEvent(Events::FlagCaptured, &toSend);
```
When making an event *connection* so we can receive an event you may use:

```
Zero::Connect(target, Events::FlagCaptured, this, &self_type::OnFlagCaptured);
```

The `target` in this case is an object that is going to have that event sent to it. We pass in `this` because we want to listen for the event. The type `self_type` is automatically declared on our class by `ZeroDeclareType`. The `&self_type::OnFlagCaptured` is C++ syntax for getting a member function pointer.

Technically `Zero::Connect` can connect any two objects (it doesn't even have to be yourself), however since your own object is most common, we have a macro to simplify this:

```
ConnectThisTo(target, Events::FlagCaptured, OnFlagCaptured);
```

Event Dispatcher/Receiver
-------------------------
In order to send events we must have an `EventDispatcher`, and in order to receive events we must have an `EventReceiver`. To make life simple, most classes can just inherit from `EventObject` which contains both of these and has all the basic functions on it. Note that `Cog` itself is actually an `EventObject` as are many other classes in the engine.

WARNING: `Component` is not an `EventObject`, however it redirects its `EventDispatcher` and `EventReceiver` to the owning `Cog`. This means that if you send an event to a particular component it actually just sends to the entire `Cog`. Similarly, if you listen for an event on a component, you are actually listening to the event on the entire `Cog`.

All events in Zero are sent and received by string names. We are able to keep this calls very efficient because we implemented our own `String` class with the following features:

- Strings are immutable and cannot be changed after they are created
- We pre-compute the hash and string length of every string we create
- Strings are reference counted (passing by value does not require allocation)
- Our HashMap is specifically optimized to make String lookup efficient

Many event systems will pass multiple arguments and invoke functions directly:

```
void MyCallback(float frameTime, int frameNumber, World* world);
```

We chose not to do this pattern because it breaks user's code easily if we need to add/remove/change the parameters in any ways. To mitigate this we chose to use a base class `Event` for the event data. All events sent must publicly inherit from `Event`. Note that you are not required to create a new derived class in order to send an event.

Events are automatically disconnected if either the sender or receiver is destructed.
 

 