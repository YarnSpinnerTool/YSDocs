# Node

Class in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A node of Yarn script, contained within a  <a href="yarn.program.md">Program</a> , and
containing  <code>Yarn.Instruction</code> s.


```csharp
public class Node
```

## Methods

|Name|Description|
|:---|:---|
|[ToString()](/docs/api/csharp/yarn.node.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Headers](/docs/api/csharp/yarn.node.headers.md)||
|[Instructions](/docs/api/csharp/yarn.node.instructions.md)|The list of instructions in this node.|
|[Labels](/docs/api/csharp/yarn.node.labels.md)|A jump table, mapping the names of labels to positions in the instructions list.|
|[Name](/docs/api/csharp/yarn.node.name.md)|The name of this node.|
|[SourceTextStringID](/docs/api/csharp/yarn.node.sourcetextstringid.md)|the entry in the program's string table that contains the original text of this node; null if this is not available|
|[Tags](/docs/api/csharp/yarn.node.tags.md)|The tags associated with this node.|

