# Node Class

A [node]({{<ref "/docs/writing/nodes-and-content.md#nodes">}}), contained within a [`Program`](/api/csharp/yarn/program.md), and containing [`Instruction`](/api/csharp/yarn/instruction.md)s.


```csharp
public sealed class Node : IMessage<Node>, IMessage, IEquatable<Node>, IDeepCloneable<Node>
```



## Properties
|Name|Description|
|:---|:---|
|[`Instructions`](/api/csharp/yarn/node.instructions.md)| The list of instructions in this node. |
|[`Labels`](/api/csharp/yarn/node.labels.md)| A jump table, mapping the names of labels to positions in the instructions list. |
|[`Name`](/api/csharp/yarn/node.name.md)| The name of this node. |
|[`SourceTextStringID`](/api/csharp/yarn/node.sourcetextstringid.md)| the entry in the program's string table that contains the original text of this node; null if this is not available     |
|[`Tags`](/api/csharp/yarn/node.tags.md)| The tags associated with this node. |
<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L247), line 247.
