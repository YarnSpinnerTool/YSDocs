# Node

Class in [Yarn](/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A [node]({{|ref "/docs/writing/nodes-and-content.md#nodes"|}}), contained within a  <a href="yarn.program.md">Program</a> , and containing  <code>Yarn.Instruction</code> s.


```csharp
public class Node
```

## Properties

|Name|Description|
|:---|:---|
|[Instructions](/api/csharp/yarn.node.instructions.md)|The list of instructions in this node.|
|[Labels](/api/csharp/yarn.node.labels.md)|A jump table, mapping the names of labels to positions in the instructions list.|
|[Name](/api/csharp/yarn.node.name.md)|The name of this node.|
|[SourceTextStringID](/api/csharp/yarn.node.sourcetextstringid.md)|the entry in the program's string table that contains the original text of this node; null if this is not available|
|[Tags](/api/csharp/yarn.node.tags.md)|The tags associated with this node.|

## Methods

|Name|Description|
|:---|:---|
|[ToString()](/api/csharp/yarn.node.tostring.md)||

