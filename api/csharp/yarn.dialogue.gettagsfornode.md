# Dialogue.GetTagsForNode(string)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Returns the tags for the node 'nodeName'.


```csharp
public IEnumerable<string> GetTagsForNode(string nodeName)
```

## Remarks


The tags for a node are defined by setting the `tags`
[header]({{|ref "/docs/syntax.md#header"|}}) in the node's
source code. This header must be a space-separated list.


## Parameters

|Name|Description|
|:---|:---|
|nodeName|The name of the node.|

## Returns

The node's tags, or `null` if the node is not present
in the Program.

