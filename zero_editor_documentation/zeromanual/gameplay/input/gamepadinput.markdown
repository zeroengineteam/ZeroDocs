[Gamepads](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepad.markdown) are very useful tools for any game project. They often offer a more comfortable method of controlling a game, especially if two or more players are intended to play at the same time. As well as being an alternate method of control, Gamepads can also make use of vibration as a method of feedback.

 # Common Uses
 - Provides a alternative method of control to Keyboard and Mouse inputs
 - Lets multiple players comfortably play a game on the same screen
 - Gives access to vibration for tactile feedback to players

 ## Before Using Gamepads
Before starting to use Gamepads in a project, take the time to check that they are properly working. What may be thought to be an error in code may, in fact, be that the Gamepad is not plugged in properly, has outdated drivers, etc. Most wired Gamepads should work without issue; however, some wireless Gamepads may need to have drivers updated. This page was written using wired XBox 360 controllers. If using an XBox One Gamepad, drivers may be found [here ](http://support.xbox.com/en-US/xbox-one/accessories/controller-pc-compatibility).


 # Using Gamepads
 ## Initial Setup
Unlike most things in Zero, it's not possible to make a simple reference to `Zero.Gamepads` and have the Engine understand what is meant, even if only a single Gamepad is connected. Rather, whenever any number of Gamepads are detected, Zero will store them in a list that must be accessed to select the desired Gamepad. 

```
class GamepadLogic : ZilchComponent
{
    // Create a variable to later use as reference to the Gamepad
    var Controller : Gamepad = null;
    // Set a Speed property to be used to adjust the movement speed
    [Property]
    var Speed : Real = 0.0;
    function Initialize(init : CogInitializer)
    {
        // Assign the first Gamepad detected as the Gamepad this object will use
        this.Controller = Zero.Gamepads.GetGamePad(0);
    }
}
```


`Zero.Gamepads` is a reference to the ZeroObject `Gamepads`, which keeps track of all detected Gamepads. The `GetGamePad` function will return a reference to whichever Gamepad corresponds to the ID passed to the function. In the case above, the Gamepad in the first element (at index 0 in the list) is accessed. `Zero.Gamepads` is a helpful reference to remember for the future, as it can be used to affect all Gamepads at once. 

 ## Reading from Thumbsticks
Thumbsticks on a Gamepad are typically used for moving the player or aiming. When accessed, they return a normalized 2D vector that is stored in corresponding `LeftStick` and `RightStick` Real2 variables on each Gamepad object. 

```
function OnLogicUpdate(event : UpdateEvent)
{
    // Create a local variable to be used for movement
    var movement = local Real3(0.0, 0.0, 0.0);

    // Check to make sure that the Gamepad exists
    if (this.Controller.IsActive)
    {
        // Assign the current direction of the Left thumbstick to the movement variable
        movement.X += this.Controller.LeftStick.X;
        movement.Y += this.Controller.LeftStick.Y;
    }
    // Apply this movement to the Velocity of the Game Objects RigidBody, multiplied by the Speed
    this.Owner.RigidBody.Velocity = movement * event.Dt * this.Speed;
}
```


Since the thumbsticks return a Real2 at a range from `-1` to `1`, this can easily be translated into creating movement on a 2D plane. Keep in mind this example does not use the `RightStick`, only the `LeftStick`. 

 ## Button Input
Similar to [Mouse Input](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/gameplay/input/mouseinput.markdown), assigning logic to the various buttons on the Gamepad can be Frame Based or Event Based. Both have their strengths and weaknesses; determining which approach is better for a specific project should be decided on a case by case basis. 

 ## Frame Based Button Input
The example given above is Frame Based, and the reason for that is simple: Frame Based Input from a Gamepad works best when there will be sustained action, such as when a thumbstick is held down to move a player character. This same logic applies to buttons as well. 

```
    function OnLogicUpdate(event : UpdateEvent)
    {
        if (this.Controller.IsButtonDown(Buttons.A))
        {
            // Insert code here
        }
    }

```


(NOTE) **Using Buttons in Zero Engine**: Zero Engine has an enum set up to be used to call a desired button, which can be accessed in a ZilchScript with `Buttons` followed by a period (e.g., `Buttons.X`). It should be noted however that the list of buttons specifically refers to the button layout of an Xbox 360 Gamepad, and may not be accurate for other Gamepads. 
This particular line of code will simply trigger whatever is placed inside the `if` statement whenever the `A` button on the Gampad is held down. `Buttons` can be changed to refer to any button on the Gamepad. `Buttons.AnyButton` can also be used if it doesn't matter which button is pressed, such as at a title screen. 

 ## Event Based Button Input
When looking for a single press or release of a button to trigger a function, Event Based Input is a better choice. In this approach, the component listens for a gamepad event dispatch, rather than checking every frame to see if a change has occurred.

```
function Initialize(init : CogInitializer)
{
    Zero.Connect(this.Controller, Events.ButtonDown, this.OnButtonDown);
    Zero.Connect(this.Controller, Events.ButtonUp, this.OnButtonUp);
}
function OnButtonDown(event : GamepadEvent)
{
    if (event.Button == Buttons.B)
    {
        // Insert code here
    }
}
function OnButtonUp(event : GamepadEvent)
{
    if (event.Button == Buttons.B)
    {
        // Insert code here
    }
}
```


This block of code first connects to two different events: `ButtonDown` and `ButtonUp`. These events will be sent whenever a button on the Gamepad has been either pressed or let go, respectively. If it is the B button, `OnButtonDown` or `OnButtonUp` will run. A short example of this functionality: an attack charges as long as a button is held down; the attack is then used when the button is released. 

NOTE: **Using Triggers in Zero Engine** By looking at the options that come up by typing `Buttons.` into a ZilchScript, one may notice that neither of the Xbox 360 Triggers are options. This is because they return a Real instead of a `boolean`. While this excludes them from sending any Events, it also allows them to be used as pressure sensitive buttons, as can be seen below in the Vibration section. 

 ### Flicking


Flicking is a Gamepad event that is sent whenever a thumbstick moves further than `0.5` is any direction. Because of how the event associated with flicking is dispatched--immediately and automatically once the stick goes past the "halfway point"--it should usually be used on whichever thumbstick is not being used for movement. 

```
function Initialize(init : CogInitializer)
{
    Zero.Connect(this.Controller, Events.GamepadStickFlicked, this.OnGamepadStickFlicked);
}

function OnGamepadStickFlicked(event : GamepadEvent)
{
    // Left thumbstick
    if(event.FlickedStick == 1)
    {
        // Insert code here
    }
     // Right thumbstick
    if(event.FlickedStick == 2)
    {
        // Insert code here
    }
}
```


This event is useful for something like a dodging mechanic, as it can be called side by side with an UpdateEvent (e.g., LogicUpdate), allowing for normal movement to continue at the same time. 

 ## Vibration
Provided that the Gamepad being used has a Vibration feature, Zero simply needs a function call to access it. As it is a physical reaction, however, an example works best to explain.

```
function OnLogicUpdate(event : UpdateEvent)
{
    // Amount of time to spend vibrating
    var vibrationTime = 1;

     this.Controller.Vibrate(vibrationTime,  // Time to vibrate for
                            this.Controller.LeftTrigger,  // Left-Side Vibration
                            this.Controller.RightTrigger); // Right-Side Vibration
}
```


This will cause the controller to vibrate whenever either the left or right triggers are depressed on the Gamepad. The second and third parameters for `Vibrate()` are Reals that define the intensity of the vibration. In the example abovea, as the triggers are pressed in further, the value they return slowly rises from `0` (not pressed) to `1` (fully depressed). As the value rises, the vibration will become stronger as the value moves towards `1`, with each trigger controlling the vibration on their respective sides.

Most Gamepads that have vibration functionality will create it by utilizing two motors housed in the casing, oftentimes with one side slightly heavier than the other (typically the left side). This allows for numerous different combinations of tactile feedback to be created, such as if the player is hit:

```
    function OnCollisionStarted(event : CollisionEvent)
    {
        this.Controller.Vibrate(0.25,  // Time to vibrate for
                                1,     // Left-Side Vibration
                                0.5);  // Right-Side Vibration
    }

```


which will cause the controller to vibrate for a quarter of a second, with the left side vibrating at full power and the right side vibrating at half. 

 ## Using Multiple Gamepads
When using multiple Gamepads, Zero will need to keep a reference of which object is associated with which Gamepad. This is easily done with the addition of a Property. 

```
// Which Gamepad is meant to control this object
[Property]
var PlayerIndex : Integer = 0;

var Controller : Gamepad = null;

function Initialize(init : CogInitializer)
{
    this.Controller = Zero.Gamepads.GetGamePad(this.PlayerIndex);
}
```


Simply change the PlayerIndex of an object to assign it to Gamepad One, Gamepad Two, etc. Keep in mind, however, that the GamePad index starts at `0`, so the index for GamePad One would be `0`, GamePad Two would be `1`, Three `2`, and so on.

 # Properties of Gamepad and Object Events
All of the events associated with the Gamepad are [GamepadEvents](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepadevent.markdown), with the exception of [GamepadUpdated](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepadevent.markdown), which is an [ObjectEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/objectevent.markdown). As all the others are the same type of event, they all share the same properties that can be accessed when the event is dispatched. `ObjectEvents` themselves can access the Gamepad that dispatched the event by using  `ObjectEvent`, which `GamepadEvents` likewise has access to with `GamepadEvent.Gamepad`.

IMPORTANT: As of the time of the creation of this page, `ObjectEvent.Source` returns a null pointer rather than the Gamepad that dispatched the event. 

Both of these can be used to trigger the same functions, the main difference being `GamepadEvent.Gamepad` would need to be triggered by the specific Gamepad, while `ObjectEvent.Source` could be used for a general script that runs the logic for multiple Gamepads during a GameSession. 

`GamepadEvents` can also reference the button used to dispatch the event with `GamepadEvent.Button`, which returns an int referring to the triggering button. The last two references all `GamepadEvents` have can only be used by the `GamepadStickFlicked` event: `FlickDirection`, which returns a Real2 of the direction the thumbstick moved in; and `FlickedStick`, which returns a reference to the thumbstick that dispatched the event. These can be used together to create movement mechanics very easily.

```
function OnGamepadStickFlicked(event : GamepadEvent)
{        
    var movement = local Real3(0.0, 0.0, 0.0);
    // Assign the X and Y values of the moved thumbstick to the local movement variable
    movement.X += event.FlickDirection.X;
    movement.Y += event.FlickDirection.Y;
    //This uses the right thumbstick, while the left is 1
    if(event.FlickedStick == 2)
    {
        // "Teleport" to a further away location
        // note no Dt, so it'll be approx 60x further than normal
        this.Owner.RigidBody.Velocity = movement * this.Speed;
    }
}
```


 ## Gamepad Events
*    `GamepadUpdated` : `ObjectEvent`
    * An event dispatched to an object whenever the Gamepad updates. Runs every frame. 

*    `ButtonDown` : `GamepadEvent`
    * An event dispatched when any button is pressed on the connected Gamepad. 

*    `ButtonUp` : `GamepadEvent`
    * An event dispatched when any button is released on the connected Gamepad. 

*    `GamepadStickFlicked` : `GamepadEvent`
    * An event dispatched when either thumbstick on the connected Gamepad is pushed forward more than halfway to its max. 

 # Related Materials
 ## Manual
- [Mouse Input](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/gameplay/input/mouseinput.markdown)

 ## Code Reference
- [Gamepad](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Gamepad.markdown) 
- [Gamepads](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Gamepads.markdown) 
- [Real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown) 
- [ObjectEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ObjectEvent.markdown) 
- [GamepadEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/gamepadevent.markdown) 

 