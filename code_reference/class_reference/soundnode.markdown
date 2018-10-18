 `Sound`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddInputNode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#addinputnode-void)|[ AutoCollapse](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#autocollapse-zero-engine)|[referencecountedeventobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/referencecountedeventobject.markdown)|[additivesynthnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/additivesynthnode.markdown)|
|[ InsertNodeAfter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#insertnodeafter-void)|[ BypassPercent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#bypasspercent-zero-engin)| |[addnoisenode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/addnoisenode.markdown)|
|[ InsertNodeBefore](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#insertnodebefore-void)|[ BypassValue](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#bypassvalue-zero-engine)| |[bandpassnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/bandpassnode.markdown)|
|[ RemoveAllInputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#removeallinputs-void)|[ HasInputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#hasinputs-zero-engine-do)| |[chorusnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/chorusnode.markdown)|
|[ RemoveAllOutputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#removealloutputs-void)|[ HasOutputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#hasoutputs-zero-engine-d)| |[compressornode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/compressornode.markdown)|
|[ RemoveAndAttachInputsToOutputs](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#removeandattachinputstoo)|[ InputCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#inputcount-zero-engine-d)| |[customaudionode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/customaudionode.markdown)|
|[ RemoveInputNode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#removeinputnode-void)|[ OutputCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#outputcount-zero-engine)| |[delaynode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/delaynode.markdown)|
|[ ReplaceWith](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown#replacewith-void)| | |[equalizernode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/equalizernode.markdown)|
| | | |[expandernode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/expandernode.markdown)|
| | | |[flangernode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/flangernode.markdown)|
| | | |[generatedwavenode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/generatedwavenode.markdown)|
| | | |[granularsynthnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/granularsynthnode.markdown)|
| | | |[highpassnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/highpassnode.markdown)|
| | | |[lowpassnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/lowpassnode.markdown)|
| | | |[microphoneinputnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/microphoneinputnode.markdown)|
| | | |[modulationnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/modulationnode.markdown)|
| | | |[panningnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/panningnode.markdown)|
| | | |[pitchnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/pitchnode.markdown)|
| | | |[recordingnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/recordingnode.markdown)|
| | | |[reverbnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/reverbnode.markdown)|
| | | |[saveaudionode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/saveaudionode.markdown)|
| | | |[volumenode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/volumenode.markdown)|


 #  Properties


---  
 #  AutoCollapse : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> If true, this node will automatically remove itself from the graph when its last input node is removed.
> ``` lang=cpp, name=Zilch
> var AutoCollapse : Boolean


---  
 #  BypassPercent : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> DEPRECATED The BypassValue property should be used instead.
> ``` lang=cpp, name=Zilch
> var BypassPercent : Real


---  
 #  BypassValue : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The percentage of output (0 to 1.0) that should skip whatever processing the node does.
> ``` lang=cpp, name=Zilch
> var BypassValue : Real


---  
 #  HasInputs : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Will be true if this node has any input nodes.
> ``` lang=cpp, name=Zilch
> var HasInputs : Boolean


---  
 #  HasOutputs : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Will be true if this node has any output nodes.
> ``` lang=cpp, name=Zilch
> var HasOutputs : Boolean


---  
 #  InputCount : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The number of input nodes that are currently attached to this node.
> ``` lang=cpp, name=Zilch
> var InputCount : Integer


---  
 #  OutputCount : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The number of output nodes that are currently attached to this node.
> ``` lang=cpp, name=Zilch
> var OutputCount : Integer


---  
 #  Methods


---  
 #  AddInputNode : Void

> Adds the passed in node to this node's inputs.
> |Name|Type|Description|
> |---|---|---|
> |node|[soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddInputNode(node : SoundNode)
> ``` 


---  
 #  InsertNodeAfter : Void

> Inserts the passed in node after this node in the signal path, placing it between this node and any nodes which were connected to this node's output.
> |Name|Type|Description|
> |---|---|---|
> |node|[soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)| |
> ``` lang=cpp, name=Zilch
> function InsertNodeAfter(node : SoundNode)
> ``` 


---  
 #  InsertNodeBefore : Void

> Inserts the passed in node before this node in the signal path, placing it between this node and any nodes which were connected to this node as inputs.
> |Name|Type|Description|
> |---|---|---|
> |node|[soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)| |
> ``` lang=cpp, name=Zilch
> function InsertNodeBefore(node : SoundNode)
> ``` 


---  
 #  RemoveAllInputs : Void

> Removes the connections between this node and all of its input nodes.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RemoveAllInputs()
> ``` 


---  
 #  RemoveAllOutputs : Void

> Removes the connections between this node and all of its output nodes, disconnecting this node from the graph. If this node has no inputs it will be deleted when no longer referenced.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RemoveAllOutputs()
> ``` 


---  
 #  RemoveAndAttachInputsToOutputs : Void

> Removes this node from the graph by disconnecting it from all inputs and outputs and attaching the input nodes to the output nodes, keeping the rest of the graph intact. This node will be deleted when it is no longer referenced.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RemoveAndAttachInputsToOutputs()
> ``` 


---  
 #  RemoveInputNode : Void

> Removes the node passed in as a parameter from this node's inputs.
> |Name|Type|Description|
> |---|---|---|
> |node|[soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveInputNode(node : SoundNode)
> ``` 


---  
 #  ReplaceWith : Void

> Replaces this node in the graph with the node passed in as a parameter. This node will be deleted when it is no longer referenced.
> |Name|Type|Description|
> |---|---|---|
> |node|[soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)| |
> ``` lang=cpp, name=Zilch
> function ReplaceWith(node : SoundNode)
> ``` 


---  
 

 