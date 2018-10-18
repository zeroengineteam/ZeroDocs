 `Engine`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ CrashEngine](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#crashengine-void)|[ GameSessions](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#gamesessions-zero-engine)|[eventobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventobject.markdown)| |
|[ CreateGameSession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#creategamesession-zero-e)| | | |
|[ CreateGameSessionFromArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#creategamesessionfromarc)| | | |
|[ DebugBreak](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#debugbreak-void)| | | |
|[ GetCurrentInputDevice](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#getcurrentinputdevice-ze)| | | |
|[ RebuildArchetypes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#rebuildarchetypes-void)| | | |
|[ Terminate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/engine.markdown#terminate-void)| | | |


 #  Properties


---  
 #  GameSessions : [gamesessionrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gamesessionrange.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var GameSessions : GameSessionRange


---  
 #  Methods


---  
 #  CrashEngine : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CrashEngine()
> ``` 


---  
 #  CreateGameSession : [gamesession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gamesession.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateGameSession() : GameSession
> ``` 


---  
 #  CreateGameSessionFromArchetype : [gamesession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gamesession.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/archetype.markdown)| |
> ``` lang=cpp, name=Zilch
> function CreateGameSessionFromArchetype(p0 : Archetype) : GameSession
> ``` 


---  
 #  DebugBreak : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugBreak()
> ``` 


---  
 #  GetCurrentInputDevice : [InputDevice](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#inputdevice)

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GetCurrentInputDevice() : InputDevice
> ``` 


---  
 #  RebuildArchetypes : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/archetype.markdown)| |
> ``` lang=cpp, name=Zilch
> function RebuildArchetypes(p0 : Archetype)
> ``` 


---  
 #  Terminate : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Terminate()
> ``` 


---  
 

 