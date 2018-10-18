Quit Messages are sent by the engine to quit out of a game by closing Game window. This happens by default when the `esc` (escape) key is pressed in game. Using the [ GameRequestQuit  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#gamerequestquit) event, however, gives the user control over the `esc` key press (which is otherwise inaccessible by Keyboard events). When connecting to the `GameRequestQuit` event, the user may assign any activity to the `esc` key that they wish. 

 # Common Uses
 - Using the `esc` key to pause the game
 - Using the `esc` key to pause the game and bring up a confirmation-of-destructive-action window
 - Using the `esc` key to to exit out of the current level

 # How to Use the GameRequestQuit Event
This section will cover connecting to the event and setting up the response function.

 ## Connecting to the GameRequestQuit Event
When connecting to the GameRequestQuit, it must be listening for the `Events.GameRequestQuit` dispatch (which is done by pressing the `esc` key) onto `this.GameSession`, as follows:

```lang=csharp
//Listening for Events.GameRequestQuit dispatch onto this.GameSession
Zero.Connect(this.GameSession, Events.GameRequestQuit, this.OnGameRequestQuit);
```

 ## The GameRequestQuit Response Function
The `GameRequestQuit` event is of type [GameEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/gameevent.markdown)  that includes a few properties that can be used inside the response function. The most notable of these, for the purposes of removing the game-exiting functionality, is `event.Handled`. `Handled` is a boolean that if set to `true`, tells the engine that the behavior for the `esc` key will now **be handled** by the code inside the response function. If `event.Handled` is left `false`, the event would persist to be handled by the engine (once again performing the default behavior of closing the `Game Window` *after* your response function completed).
The following will code-block will show how the response function can create alternate behavior for the `esc` key while still allowing for game-quitting functionality:

```
class GameQuitTest : ZilchComponent
{
    // Boolean variable that when set to true, Esc key will keep game-quitting functionality
    [Property]
    var ApplyQuit : Boolean = false;

    function Initialize(init : CogInitializer)
    {
         // Listening for Events.GameRequestQuit dispatch onto this.GameSession
        Zero.Connect(this.GameSession, Events.GameRequestQuit, this.OnGameRequestQuit);
    }
    function OnGameRequestQuit(event : GameEvent)
    {
        // Let the engine know that this function will handle behavior for the Esc key
        event.Handled = true;
        // If this.ApplyQuit is set to true...
        if(this.ApplyQuit)
        {
            // Call function to quit game from the GameSession object
            event.Game.Quit();
        }
        // If this.ApplyQuit is set to false...
        else
        {
            // Supply alternate behavior (pausing/unpausing the game) for Esc key
            var spaces = this.GameSession.AllSpaces;
            foreach (var space in spaces)
            {
                space.TimeSpace.TogglePause();
            }
        }
    }
}
```


 # Related Materials
 ## Manual Pages
- [Events and Connections](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/scripting/eventsandconnections.markdown)

 ## Code Reference
- [GameEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/gameevent.markdown) 
- [ GameRequestQuit  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#gamerequestquit)

 

 