 `Engine`

(NOTE) Game Object Composition class. This class is the foundational object for all dynamic objects in the game world. The Cog is a piece of logical interactive content and the primary mechanism game systems (Graphics, Physics, Etc.) provide functionality and communicate. A Cog can be anything from physical objects like trees, tanks, players to logical objects like teams, triggers, or AI objects.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddComponentByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#addcomponentbyname-zero)|[ Actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#actions-zero-engine-docu)|Object|[gamesession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gamesession.markdown)|
|[ AddComponentByType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#addcomponentbytype-zero)|[ Archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#archetype-zero-engine-do)| |[space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/space.markdown)|
|[ AttachTo](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#attachto-zero-engine-doc)|[ BaseArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#basearchetype-zero-engin)| | |
|[ AttachToPreserveLocal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#attachtopreservelocal-ze)|[ ChildCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#childcount-zero-engine-d)| | |
|[ ClearArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#cleararchetype-void)|[ Children](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#children-zero-engine-doc)| | |
|[ Clone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#clone-zero-engine-docume)|[ ComponentCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#componentcount-zero-engi)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#cog-void)|[ EditorViewportHidden](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#editorviewporthidden-zer)| | |
|[ DebugDraw](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#debugdraw-void)|[ GameSession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#gamesession-zero-engine)| | |
|[ Destroy](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#destroy-void)|[ LevelSettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#levelsettings-zero-engin)| | |
|[ Detach](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#detach-void)|[ Locked](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#locked-zero-engine-docum)| | |
|[ DetachPreserveLocal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#detachpreservelocal-void)|[ MarkedForDestruction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#markedfordestruction-zer)| | |
|[ DispatchDown](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#dispatchdown-void)|[ Name](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#name-zero-engine-documen)| | |
|[ DispatchEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#dispatchevent-void)|[ ObjectViewHidden](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#objectviewhidden-zero-en)| | |
|[ DispatchUp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#dispatchup-void)|[ Parent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#parent-zero-engine-docum)| | |
|[ FindAllChildrenByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findallchildrenbyname-ze)|[ Persistent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#persistent-zero-engine-d)| | |
|[ FindChildByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findchildbyname-zero-eng)|[ RuntimeId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#runtimeid-zero-engine-do)| | |
|[ FindDirectChildByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#finddirectchildbyname-ze)|[ Space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#space-zero-engine-docume)| | |
|[ FindNearestArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findnearestarchetype-zer)|[ Transient](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#transient-zero-engine-do)| | |
|[ FindNextInOrder](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findnextinorder-zero-eng)| | | |
|[ FindNextSibling](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findnextsibling-zero-eng)| | | |
|[ FindPreviousInOrder](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findpreviousinorder-zero)| | | |
|[ FindPreviousSibling](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findprevioussibling-zero)| | | |
|[ FindRoot](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findroot-zero-engine-doc)| | | |
|[ FindRootArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#findrootarchetype-zero-e)| | | |
|[ GetComponentByIndex](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#getcomponentbyindex-zero)| | | |
|[ GetComponentByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#getcomponentbyname-zero)| | | |
|[ GetComponentIndex](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#getcomponentindex-zero-e)| | | |
|[ IsAncestorOf](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#isancestorof-zero-engine)| | | |
|[ IsDescendant](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#isdescendant-zero-engine)| | | |
|[ IsDescendantOf](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#isdescendantof-zero-engi)| | | |
|[ IsModifiedFromArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#ismodifiedfromarchetype)| | | |
|[ PlaceAfterSibling](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#placeaftersibling-void)| | | |
|[ PlaceBeforeSibling](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#placebeforesibling-void)| | | |
|[ RemoveComponentByName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#removecomponentbyname-ze)| | | |
|[ RemoveComponentByType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#removecomponentbytype-ze)| | | |
|[ ReplaceChild](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#replacechild-void)| | | |
|[ SanitizeName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#sanitizename-zero-engine)| | | |
|[ UploadToArchetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown#uploadtoarchetype-void)| | | |


 #  Properties


---  
 #  Actions : [actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/actions.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Actions : Actions


---  
 #  Archetype : [archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/archetype.markdown)

> Getter / setter for Archetype.
> ``` lang=cpp, name=Zilch
> var Archetype : Archetype


---  
 #  BaseArchetype : [archetype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/archetype.markdown)

 `read-only`

> Returns the Archetype our Archetype inherits from.
> ``` lang=cpp, name=Zilch
> var BaseArchetype : Archetype


---  
 #  ChildCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns the amount of children on this Cog. Note that this function has to iterate over all children to calculate the count.
> ``` lang=cpp, name=Zilch
> var ChildCount : Integer


---  
 #  Children : [hierarchylistrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/hierarchylistrange.markdown)

 `read-only`

> Returns a range of all direct children on this Cog.
> ``` lang=cpp, name=Zilch
> var Children : HierarchyListRange


---  
 #  ComponentCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns how many Components are on this Cog.
> ``` lang=cpp, name=Zilch
> var ComponentCount : Integer


---  
 #  EditorViewportHidden : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Hidden from view used for editor.
> ``` lang=cpp, name=Zilch
> var EditorViewportHidden : Boolean


---  
 #  GameSession : [gamesession](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gamesession.markdown)

 `read-only`

> Get the GameSession that owns us and our Space.
> ``` lang=cpp, name=Zilch
> var GameSession : GameSession


---  
 #  LevelSettings : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Get the object named 'LevelSettings', a special convenience object where we can put general functionality for our Level.
> ``` lang=cpp, name=Zilch
> var LevelSettings : Cog


---  
 #  Locked : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Not able to be modified or selected in the viewport.
> ``` lang=cpp, name=Zilch
> var Locked : Boolean


---  
 #  MarkedForDestruction : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Has this Cog already been destroyed and is waiting for the frame to end (delayed destruction). This allows us to do custom logic when an object is still not null, but about to be destroyed (e.g. we don't want to render Cogs marked for deletion).
> ``` lang=cpp, name=Zilch
> var MarkedForDestruction : Boolean


---  
 #  Name : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> Name of the Object.
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  ObjectViewHidden : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If the object needs to not show up in the object view.
> ``` lang=cpp, name=Zilch
> var ObjectViewHidden : Boolean


---  
 #  Parent : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Get the parent of this object in the Hierarchy.
> ``` lang=cpp, name=Zilch
> var Parent : Cog


---  
 #  Persistent : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Object will not be destroyed on level load or change.
> ``` lang=cpp, name=Zilch
> var Persistent : Boolean


---  
 #  RuntimeId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Gets a unique integer for this object (used primarily for debugging)
> ``` lang=cpp, name=Zilch
> var RuntimeId : Integer


---  
 #  Space : [space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/space.markdown)

 `read-only`

> Returns the Space that this object lives in.
> ``` lang=cpp, name=Zilch
> var Space : Space


---  
 #  Transient : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Object will not be saved.
> ``` lang=cpp, name=Zilch
> var Transient : Boolean


---  
 #  Methods


---  
 #  AddComponentByName : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Add a component by name.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddComponentByName(name : String) : Boolean
> ``` 


---  
 #  AddComponentByType : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Add a component of the given type.
> |Name|Type|Description|
> |---|---|---|
> |componentType|[boundtype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boundtype.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddComponentByType(componentType : BoundType) : Boolean
> ``` 


---  
 #  AttachTo : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Attach to a parent object and compute the new transform so that the objects are relative.
> |Name|Type|Description|
> |---|---|---|
> |parent|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function AttachTo(parent : Cog) : Boolean
> ``` 


---  
 #  AttachToPreserveLocal : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Attach to a parent object.
> |Name|Type|Description|
> |---|---|---|
> |parent|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function AttachToPreserveLocal(parent : Cog) : Boolean
> ``` 


---  
 #  ClearArchetype : Void

> Removes our association with the current Archetype.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearArchetype()
> ``` 


---  
 #  Clone : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Clones this cog. The cloned object will be parented to this objects parent (if it exists).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clone() : Cog
> ``` 


---  
 #  Cog : Void

 `constructor`

> Constructor / destructor.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Cog()
> ``` 


---  
 #  DebugDraw : Void

> Calls DebugDraw on all components in this cog.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugDraw()
> ``` 


---  
 #  Destroy : Void

> Queues the cog up for delayed destruction (at the end of the frame). If the object is marked as Protected, this will do nothing.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Destroy()
> ``` 


---  
 #  Detach : Void

> Detach from a parent object and compute the new transform so that the objects are relative.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Detach()
> ``` 


---  
 #  DetachPreserveLocal : Void

> Detach from a parent object.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DetachPreserveLocal()
> ``` 


---  
 #  DispatchDown : Void

> Dispatches an event down the tree on all children recursively (pre-order traversal)
> |Name|Type|Description|
> |---|---|---|
> |eventId|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |event|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
> ``` lang=cpp, name=Zilch
> function DispatchDown(eventId : String, event : Event)
> ``` 


---  
 #  DispatchEvent : Void

> Dispatches an event on this object.
> |Name|Type|Description|
> |---|---|---|
> |eventId|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |event|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
> ``` lang=cpp, name=Zilch
> function DispatchEvent(eventId : String, event : Event)
> ``` 


---  
 #  DispatchUp : Void

> Dispatches an event up the tree on each parent recursively (pre-order traversal)
> |Name|Type|Description|
> |---|---|---|
> |eventId|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |event|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
> ``` lang=cpp, name=Zilch
> function DispatchUp(eventId : String, event : Event)
> ``` 


---  
 #  FindAllChildrenByName : [hierarchynamerange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/hierarchynamerange.markdown)

> Returns a range of all children with the given name.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function FindAllChildrenByName(name : String) : HierarchyNameRange
> ``` 


---  
 #  FindChildByName : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Depth first search of all children.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function FindChildByName(name : String) : Cog
> ``` 


---  
 #  FindDirectChildByName : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Checks only direct children.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function FindDirectChildByName(name : String) : Cog
> ``` 


---  
 #  FindNearestArchetype : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Same as FindNearestParentArchetype except that it includes this Cog.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindNearestArchetype() : Cog
> ``` 


---  
 #  FindNextInOrder : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Finds the next Cog in depth first post-order.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindNextInOrder() : Cog
> ``` 


---  
 #  FindNextSibling : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Returns the sibling Cog after this in the parents child list. Returns null if it's the last child. If the Cog doesn't have a parent, it will return the Cog after it in the Space.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindNextSibling() : Cog
> ``` 


---  
 #  FindPreviousInOrder : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Finds the previous Cog in reverse depth first post-order (the opposite of FindNextInOrder).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindPreviousInOrder() : Cog
> ``` 


---  
 #  FindPreviousSibling : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Returns the sibling Cog before this in the parents child list. Returns null if it's the first child. If the Cog doesn't have a parent, it will return the Cog before it in the Space.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindPreviousSibling() : Cog
> ``` 


---  
 #  FindRoot : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Searches up the hierarchy for the root Cog.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindRoot() : Cog
> ``` 


---  
 #  FindRootArchetype : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

> Finds the top most Archetype in the Hierarchy.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FindRootArchetype() : Cog
> ``` 


---  
 #  GetComponentByIndex : [component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)

> Returns the Component at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetComponentByIndex(index : Integer) : Component
> ``` 


---  
 #  GetComponentByName : [component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)

> Finds the Components with the given type name.
> |Name|Type|Description|
> |---|---|---|
> |componentTypeName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetComponentByName(componentTypeName : String) : Component
> ``` 


---  
 #  GetComponentIndex : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> Finds the index of the given Component type. Returns uint max if the Component didn't exist.
> |Name|Type|Description|
> |---|---|---|
> |componentType|[boundtype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boundtype.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetComponentIndex(componentType : BoundType) : Integer
> ``` 


---  
 #  IsAncestorOf : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns whether or not we are an ancestor of the given Cog.
> |Name|Type|Description|
> |---|---|---|
> |descendant|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsAncestorOf(descendant : Cog) : Boolean
> ``` 


---  
 #  IsDescendant : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns whether or not the given cog is a descendant of us.
> |Name|Type|Description|
> |---|---|---|
> |cog|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsDescendant(cog : Cog) : Boolean
> ``` 


---  
 #  IsDescendantOf : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns whether or not we are a descendant of the given Cog.
> |Name|Type|Description|
> |---|---|---|
> |ancestor|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsDescendantOf(ancestor : Cog) : Boolean
> ``` 


---  
 #  IsModifiedFromArchetype : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns whether or not we have any local modifications from our Archetype. This does not account for properties with LocalModificationOverride (such as Transform modifications).
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IsModifiedFromArchetype() : Boolean
> ``` 


---  
 #  PlaceAfterSibling : Void

> Moves this Cog after the given sibling. Assumes they have the same parent.
> |Name|Type|Description|
> |---|---|---|
> |sibling|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlaceAfterSibling(sibling : Cog)
> ``` 


---  
 #  PlaceBeforeSibling : Void

> Moves this Cog before the given sibling. Assumes they have the same parent.
> |Name|Type|Description|
> |---|---|---|
> |sibling|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlaceBeforeSibling(sibling : Cog)
> ``` 


---  
 #  RemoveComponentByName : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Remove a component by name. Returns true if the component existed.
> |Name|Type|Description|
> |---|---|---|
> |typeName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveComponentByName(typeName : String) : Boolean
> ``` 


---  
 #  RemoveComponentByType : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Remove a component by type. Returns true if the component existed.
> |Name|Type|Description|
> |---|---|---|
> |componentType|[boundtype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boundtype.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveComponentByType(componentType : BoundType) : Boolean
> ``` 


---  
 #  ReplaceChild : Void

> Places the new child at the same place as the old child in the Hierarchy. This detaches but does not destroy the old child.
> |Name|Type|Description|
> |---|---|---|
> |oldChild|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> |newChild|[cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function ReplaceChild(oldChild : Cog, newChild : Cog)
> ``` 


---  
 #  SanitizeName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Cleans an object name of invalid runes.
> |Name|Type|Description|
> |---|---|---|
> |newName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function SanitizeName(newName : String) : String
> ``` 


---  
 #  UploadToArchetype : Void

> Upload this objects data to the archetype and marks this object as not modified. This function does not rebuild all other Cogs with the same Archetype. See ArchetypeRebuilder for more information about how to rebuild Archetypes.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function UploadToArchetype()
> ``` 


---  
 

 