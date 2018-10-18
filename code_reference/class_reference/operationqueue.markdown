 `Engine`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ BeginBatch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#beginbatch-void)|[ ActiveBatchName](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#activebatchname-zero-eng)|[referencecountedeventobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/referencecountedeventobject.markdown)| |
|[ ClearAll](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#clearall-void)|[ Commands](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#commands-zero-engine-doc)| | |
|[ ClearRedo](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#clearredo-void)|[ RedoCommands](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#redocommands-zero-engine)| | |
|[ ClearUndo](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#clearundo-void)| | | |
|[ DestroyObject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#destroyobject-void)| | | |
|[ EndBatch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#endbatch-void)| | | |
|[ IsListeningForSideEffects](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#islisteningforsideeffect)| | | |
|[ MarkPropertyAsModified](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#markpropertyasmodified-v)| | | |
|[ ObjectCreated](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#objectcreated-void)| | | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#operationqueue-void)| | | |
|[ PopSubPropertyContext](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#popsubpropertycontext-vo)| | | |
|[ QueueRegisteredSideEffects](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#queueregisteredsideeffec)| | | |
|[ Redo](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#redo-void)| | | |
|[ RegisterSideEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#registersideeffect-void)| | | |
|[ SaveObjectState](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#saveobjectstate-void)| | | |
|[ StartListeningForSideEffects](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#startlisteningforsideeff)| | | |
|[ Undo](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationqueue.markdown#undo-void)| | | |


 #  Properties


---  
 #  ActiveBatchName : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ActiveBatchName : String


---  
 #  Commands : [operationlistrange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationlistrange.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Commands : OperationListRange


---  
 #  RedoCommands : [operationlistrange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operationlistrange.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var RedoCommands : OperationListRange


---  
 #  Methods


---  
 #  BeginBatch : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function BeginBatch()
> ``` 


---  
 #  BeginBatch : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function BeginBatch(p0 : String)
> ``` 


---  
 #  ClearAll : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearAll()
> ``` 


---  
 #  ClearRedo : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearRedo()
> ``` 


---  
 #  ClearUndo : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearUndo()
> ``` 


---  
 #  DestroyObject : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function DestroyObject(p0 : Cog)
> ``` 


---  
 #  EndBatch : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function EndBatch()
> ``` 


---  
 #  IsListeningForSideEffects : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `static`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IsListeningForSideEffects() : Boolean
> ``` 


---  
 #  MarkPropertyAsModified : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
> |p1|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function MarkPropertyAsModified(p0 : Component, p1 : String)
> ``` 


---  
 #  ObjectCreated : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function ObjectCreated(p0 : Cog)
> ``` 


---  
 #  OperationQueue : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function OperationQueue()
> ``` 


---  
 #  PopSubPropertyContext : Void

 `static`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PopSubPropertyContext()
> ``` 


---  
 #  QueueRegisteredSideEffects : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function QueueRegisteredSideEffects()
> ``` 


---  
 #  Redo : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Redo()
> ``` 


---  
 #  Redo : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[operation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operation.markdown)| |
> ``` lang=cpp, name=Zilch
> function Redo(p0 : Operation) : Boolean
> ``` 


---  
 #  RegisterSideEffect : Void

 `static`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[anyhandle](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/anyhandle.markdown)| |
> |p1|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |p2|T| |
> ``` lang=cpp, name=Zilch
> function RegisterSideEffect(p0 : AnyHandle, p1 : String, p2 : T)
> ``` 


---  
 #  SaveObjectState : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function SaveObjectState(p0 : Cog)
> ``` 


---  
 #  StartListeningForSideEffects : Void

 `static`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StartListeningForSideEffects()
> ``` 


---  
 #  Undo : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Undo()
> ``` 


---  
 #  Undo : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[operation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/operation.markdown)| |
> ``` lang=cpp, name=Zilch
> function Undo(p0 : Operation) : Boolean
> ``` 


---  
 
  
  
  
  
  
  
  

 