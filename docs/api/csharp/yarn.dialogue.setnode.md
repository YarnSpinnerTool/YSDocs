# Dialogue.SetNode(string)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Prepares the  [Dialogue](yarn.dialogue.md)  that the user intends to start
running a node.


```csharp
public void SetNode(string startNode = DefaultStartNodeName)
```

## Remarks

<p>
After this method is called, you call [Continue()](yarn.dialogue.continue.md) to
start executing it.
</p> <p>
If [PrepareForLinesHandler](yarn.dialogue.prepareforlineshandler.md) has been set, it may be
called when this method is invoked, as the Dialogue determines which
lines may be delivered during the `startNode`
node's execution.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` startNode|The name of the node that will be run. The node have been loaded by calling  [SetProgram(Program)](yarn.dialogue.setprogram.md) .|

