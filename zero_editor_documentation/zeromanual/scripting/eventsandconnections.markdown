Events are the main way that objects and components talk to each other in the Zero Engine. When a component has information that it wants to share, the easiest way is to package the information into an Event, and then dispatch it.  Then, any component that wants to have that information can listen for it by connecting a member function to the event. In the Zero Engine, there are two main categories of events: the pre-defined Engine events (such as as an Update event or a Collision event) that are that ready-made for you to connect to, and Custom ZilchScript Events that the user creates. The Custom Events allow the user to decide when and where to send them out, what information is sent with them, and what listens for the event after it's sent. This page will briefly cover each of the two categories, but will focus specifically on Custom Events(see [event_reference](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown) for built-in events).

 # Pre-Defined Engine Events

At the bottom of this page is a comprehensive list of the pre-defined engine events. The [LogicUpdate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#logicupdate) Event, [Collision Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionevent.markdown) (which comes in three variations: Started, Ended, and Persisted), [Keyboard Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboardevent.markdown), and [Mouse Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouseevent.markdown).

 # Custom ZilchScript Events


These are the events that the user will create and dispatch themselves. A primary reason to use custom events is that they move the focus away from whatever triggers an action (such as collision or a frame update) to the object that is responding to the event occurring (i.e. the player's health and the HUD element displaying the player's health that is changed as a result of colliding with an enemy). There are a number of benefits to this approach, including:
*   One event dispatch on an object can cause many behaviors to occur.
    *   i.e. PlayersDamagedEvent is dispatched on the player object
        *   The player's hp lowers in the Health component attached to the player
        *   The object representing the player's health in the HUD scales to reflect the player's new health
        *   The AnimationController changes the player sprite to the DamagedAnimation
*   Multiple components on different objects can all respond to the same event dispatch.
*   Events can make it easier to understand and modify your code as particular behavior responses are more closely related to the objects they affect, while also encouraging logical decoupling.
Keep in mind that the user will only want to use custom events when there is more than one component "listening" for the event. The user will get the most use out of custom events when the events that are created are things that affect multiple objects in your game. Using a custom event when only one object is listening adds an unnecessary layer of abstraction, whereas a simple, direct function call to enact the desired behavior change is much simpler.

 # Using Custom Events in a Game


Let's go through a quick analogy for events. Imagine a world just like ours, but where vampires and ghosts also happen to exist alongside humans. In this instance, the custom event we are concerned with is the rising of the sun in the morning. In this world we're imagining, the appearance of the sun causes specific behaviors in some of the objects that exist in the world, but for others, it means nothing at all. For the humans, the sun rising means it is time to wake up; for the vampires, it can mean instant death if they happen to be outside; for the ghosts, it means they are banished back to the grave; for rocks, however, it means nothing at all. Humans, vampires, and ghosts all have an interest in the sun rising and will respond to it in different ways. Rocks couldn't care less.

(NOTE)**Exceptions to the Rule**: When might one want to use a custom event when there is only one object listening? Here is at least one example worth covering: When the user has a large number of instances of the same object that need to respond to some change. Using the example above, say that the world is overrun with vampires. There are hundreds swarming over an area. Once could put all instances of the vampire into an array and call the behavior-changing function on each one, but in this case it is simpler, and most likely more efficient, to just have the vampire archetype from which the instances are created have a component that listens for a "sun rises" event and changes their behavior accordingly.

This scenario could translate into a game as follows:
    *  When the sun rises, a custom event is "sent out" to the entire game space.
    *  One must then decide what objects should be "listening" for this event. In the example, all humans, vampires, and ghosts.
    *  These objects that are listening for the event respond to it in different ways, however, requiring the user to define how each separate object responds when they "hear" the event (to be written in behavior-changing functions--in the components attached to the listening objects--that are called as a result of the component "hearing" the event).
    *  All the other objects that are not affected by the event (rocks, buildings, etc...) have no need to listen to the event. Since they don't care about the event, they will have no component that even acknowledges the event was sent.

 ## Decoupling and Custom Events


To understand how Custom Events can help with Decoupling one's code, it is helpful to first have a working definition of Coupling. Two elements within a project are considered coupled if a change in one element directly leads to a change in the other element. For example, if the player object has a child object that moves one-to-one with every movement of the player (and the player moves one-to-one with every movement of the child), the movement of those two objects could be considered tightly coupled. If, on the other hand, the child's movement is not reliant upon the movement of the player, the movement of the two objects is decoupled (otherwise known as loose or low coupling); that is, the action of either object does not have a direct, corresponding effect on the other.

Custom Events allow you to decouple elements within one's game so that the emphasis lies more with those objects that are listening for an event, causing some change in behavior. The behavior change caused by listening to the event is not directly tied to the sending of the event; on the contrary, the objects that listen for the event can respond to hearing that event in completely different ways that do not affect each other and are not influenced by the sending of the event (the exception in this case being if you are attaching data with an event, as will be shown below). 

 # Event Dispatching


Events are dispatched per object. The objects that events can be dispatched on can include the Space, the Level Settings of a level, the owner of the component dispatching the event (i.e. `this.Owner`), as well as any other specific object to which one has a reference. Events dispatched onto the Space object will be heard by every object that is listening to the Space for that particular event. In short, the listener that is connecting to an event must match up that connection exactly in the way in which the event was dispatched.

(NOTE)**Consider the Following**:
    There are two red Players, Player1 and Player2. They both connect to ChangeColorToBlueEvent so they can respond with their OnChangeColorToBlueEvent functions (that, in fact, change their color blue.) When Player1 signs up for the ChangeColorToBlueEvent, it listens for the one dispatched by the **Space** object.  When Player2 signs up for the same ChangeColorToBlueEvent, it listens for the one dispatched out by the **Game** object. Later when the ChangeColorToBlueEvent is fired from the Space, Player1 changes to the color Blue having received the event, while Player2 stays red. 

 # Creating and Using Custom Script Events


The creation and usage of custom events in Zero is a multi-step process that follows a simple mechanism that relies upon correctly matching up event dispatches with event connections. The following sections will detail the way in which to correctly create, attach data to, dispatch, and connect to custom events.

WARNING: Occasionally, you will need to store information received in an event for later use. You may be tempted to store a reference to the event object itself. **This is a bad practice and should never be done.** You should instead copy the information within the received event object by value into variables of their corresponding types. 

If you were to store a reference to the event object itself the reference would lose its validity as soon as all event listeners have executed and the event is deallocated. This situation would result in the event reference to point at an address in memory that may be currently be in use by another part of the engine since it is no longer being used by the event. Accessing the broken event reference in the state will result in undefined behavior.

 ## Creating the Event Definition


The following code-block demonstrates both how to create a custom event as well as how to include data to send with the event. While it is rare that one will send no data, it is *not* necessary to include data when creating the event. In these cases, the dispatching of the event itself is the data. In most cases, however, data will be included that will have relevance to the behavior change desired by the object that is connecting to the event (i.e. on a "enemy destroyed" event, one might send the amount of points the player receives for destroying the enemy).

```
    // Define a custom ZilchEvent
    class MyCustomEvent : ZilchEvent
    {
        //Data to be sent with the event 
        //that will be used by the object connecting to the event
        var InfoToSend : String = "";
        var NumberToSend : Integer = 0;
        var RealToSend : Real = 0.0;
    }   

```


 ## Send an Event


Sending an event is a four part process. 
1. Create an event. 
2. Attach data to the event. **(optional)** 
3. Use the `sends` keyword to add the *name* of the event you're sending to the `Events` namespace. 
4. Using the appropriate event-sender, dispatch the event. 

 ## Create the Event

```
    //Create an instance of the Custom Event
    var myCustomEvent = MyCustomEvent();

```


 ## Attach Data to the Event


NOTE: Users can only add data to the member variables defined in the event's class. To add more data, the user needs to alter the event's class to include more member variables.

```
    class MyCustomEvent : ZilchEvent
    {
        //Attach Data
        myCustomEvent.InfoToSend = "data";
        myCustomEvent.NumberToSend = 5;
    }
    
    class EventDispatcher : ZilchComponent
    {
        var DataThatWillNotBeAdded : Real = 10.5;
        
        //This data WILL NOT be sent with the event
        //as it is not added within the event-defining class
        myCustomEvent.RealToSend = this.DataThatWillNotBeAdded;
    }
    

```


 ## Using the Sends Keyword


The `sends` keyword helps users in two ways. First, it registers the string type ID so that it's associated with the event type itself (allowing one to send and connect using the `Events.MyCustomEvent` syntax) while also keeping the event //type safe//; that is, an error will be thrown on the event response function if one tries to connect to an event that doesn't precisely match the method in which the event was dispatched.
Users can only use the `sends` keyword within the outermost class-scope (of either the class defining the custom event or the class in which it is dispatched), *outside of any function* within that class. In other words, it must be used outside of `Initialize`, `OnLogicUpdate`, or any other function. Placing it within the class that creates the event itself is a good way to keep track of it is registered, but ultimately it is up to the user where they wish to put it so long as it not used inside any function. The following two code-blocks show two ways to use the `sends` keyword correctly:

```
    class MyCustomEvent : ZilchEvent
    {
        //Using the sends keyword correctly within the class
        //that defines that custom event
        sends MyCustomEvent : MyCustomEvent;
    }
    

```


```
    class EventDispatcher : ZilchComponent
    {
        //Using the sends keyword correctly within the class
        //that dispatches the custom event
        sends MyCustomEvent : MyCustomEvent;
        
        function Initialize(init : CogInitializer)
        {
        }
    }

```


The following code-block will show an **incorrect** way use the `sends` keyword:

```
    class EventDispatcher : ZilchComponent
    {
        function Initialize(init : CogInitializer)
        {
            //Incorrect usage of sends keyword within a function 
            sends MyCustomEvent : MyCustomEvent;
        }
    }

```


 ## Dispatch the Event


Always be mindful of sending the events from the source one's subscribers are expecting to hear it from. 

```
class MyCustomEvent : ZilchEvent
{
  //Registers the string type ID to be associated with the event type
  sends MyCustomEvent : MyCustomEvent;
}

class EventDispatcher : ZilchComponent
{
    //Property for selecting the CogPath of the object for which to 
    //dispatch the event
    [Property]
    var ObjectToDispatchToPath : CogPath = null;
     //Cog variable for which to assign the Cog of the CogPath variable
    var ObjectToDispatchTo : Cog = null;
     function Initialize(init : CogInitializer)
    {
        //Sets Cog variable for the object to dispatch 
        //to the Cog from CogPath variable
        this.ObjectToDispatchTo = this.ObjectToDispatchToPath.Cog;
         //Create an instance of the event
        var myCustomEvent : MyCustomEvent = new MyCustomEvent();
         //Dispatches the Event onto multiple objects from component
         //Dispatch onto `this.Owner`
        this.Owner.DispatchEvent(Events.MyCustomEvent, myCustomEvent);
        //Dispatch onto LevelSettings
        this.LevelSettings.DispatchEvent(Events.MyCustomEvent, myCustomEvent);
        //Dispatch onto other, specific object
        this.ObjectToDispatchTo.DispatchEvent(Events.MyCustomEvent, myCustomEvent);
         //Dispatch onto `this.Space`
        this.Space.DispatchEvent(Events.MyCustomEvent, myCustomEvent);    
        //Dispatch onto `this.GameSession`
        this.GameSession.DispatchEvent(Events.MyCustomEvent, myCustomEvent);
    }
}    
```


 ## Listening for an Event


**In order to respond to an event, the user must identify which event-sender you are listening to:**
   Space, LevelSettings, GameSession, Object from which the event is dispatched (along with the object's parent or children), another specific object, etc.
**Which event the user cares about:**
   Events.LogicUpdate, Events.MyCustomEvent, etc.
**And how the user plans to respond:**
   OnLogicUpdate, OnMyCustomEvent, etc.

(NOTE)**Dispatching Onto Space vs LevelSettings**: One thing to keep in mind when dispatching onto either the Space or LevelSettings is the scope of each. Remember that the LevelSettings object is also scoped to the Level that it is in. This is important to consider when using custom events because if the level is changed, the particular LevelSettings object for that level will no longer exist as well as any events that were dispatched onto LevelSettings. The Space on the other hand, could continue to exist between the changing of levels and any events that dispatch onto the Space will still exist. 

Many different functions in various components can connect to the same dispatched event. All that is required is that each object have a function that is connected correctly to the single event that has been dispatched on that object.

IMPORTANT: Make sure the event connection is made in a place that will only run **once**. If the event ends up *connecting multiple times//, the object it's dispatched onto will //respond multiple times to a* **single** //event//.
While connecting to an event is usually done in a component's `Initialize` function, it doesn't have to. The connection may be dependent on other factors or variables, especially if the user wants the object to connect only after something significant has happened. In these cases, one may choose to place the connection outside of the `Initialize` function and within the scope of a conditional statement checking for certain criteria.

 ## Connecting


```
//Listening for Custom Events
//Listening for Dispatch onto `this.Owner`
Zero.Connect(this.Owner, Events.MyCustomEvent, this.OnMyCustomEvent);
//Listening for Dispatch onto `this.Space`
Zero.Connect(this.Space, Events.MyCustomEvent, this.OnMyCustomEvent);
//Listening for Dispatch onto `this.LevelSettings`
Zero.Connect(this.LevelSettings, Events.MyCustomEvent, this.OnMyCustomEvent);
//Listening for Dispatch onto `this.GameSession`
Zero.Connect(this.GameSession, Events.MyCustomEvent, this.OnMyCustomEvent);

```


 ## Responding to an Event


In order to actually respond to the event, the user needs to define the function provided in the call to Zero.Connect.
ere, one can gain access to the data that is sent with the event, for use in altering behavior or setting properties.

```
    //This function gets called because this is the one 
    //we connected to when we listened to the event
    function OnMyCustomEvent(myCustomEvent : MyCustomEvent)
    {
        //Use as much or as little information passed by the event
        this.Owner.ComponentName.PropertyName = myCustomEvent.InfoToSend;
        this.Owner.ComponentName.Value = myCustomEvent.NumberToSend;
    }   

```


 ## Disconnecting

Disconnecting makes it so one is no longer notified when the event occurs. If multiple functions are linked to the same event, these too will be disconnected. There is no way to disconnect only one connection to the event; if one is disconnected, all are disconnected. 

```
    //Disconnecting From Events    
    Zero.Disconnect(this.Owner, Events.MyCustomEvent, this);

```


Another important thing to keep in mind regarding Disconnecting is that is object-specific and event-specific but *not* receiver-specific. That is why in the code-block immediately above, only `this` is passed in as the final argument instead of the delegate itself (i.e. `this.OnMyCustomEvent`).

 # Related Material

 ## Reference
- [event_reference](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown)
- [Collision Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionevent.markdown)
- [Keyboard Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboardevent.markdown)
- [Mouse Events](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/mouseevent.markdown) 

 