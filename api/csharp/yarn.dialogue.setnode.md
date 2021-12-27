# Dialogue.SetNode(string)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Prepares the  <a href="yarn.dialogue.md">Dialogue</a>  that the user intends to
start running a node.


```csharp
public void SetNode(string startNode = DefaultStartNodeName)
```

## Remarks


After this method is called, you call  <a href="yarn.dialogue.continue.md">Continue()</a>  to
start executing it.

If  <a href="yarn.dialogue.prepareforlineshandler.md">PrepareForLinesHandler</a>  has been set, it may be
called when this method is invoked, as the Dialogue determines
which lines may be delivered during the  <code>startNode</code>  node's execution.


## Parameters

|Name|Description|
|:---|:---|
|`string` startNode|The name of the node that will be run. The node have been loaded by calling  <a href="yarn.dialogue.setprogram.md">SetProgram(Program)</a>  or  <a href="yarn.dialogue.addprogram.md">AddProgram(Program)</a> .|

