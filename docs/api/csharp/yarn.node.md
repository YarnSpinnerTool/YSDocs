# Node

Class in [Yarn](yarn.md)

Inherits from `System.Object`

## Summary

A node of Yarn script, contained within a [Program](yarn.program.md) , and containing `Yarn.Instruction` s.

```csharp
public class Node
```

## Fields

| Name                                            | Description                                                               |
| ----------------------------------------------- | ------------------------------------------------------------------------- |
| [NodeGroupHeader](yarn.node.nodegroupheader.md) | The name of the header that indicates which node group a node belongs to. |

## Methods

| Name                                | Description |
| ----------------------------------- | ----------- |
| [ToString()](yarn.node.tostring.md) |             |

## Properties

| Name                                                                                            | Description                                                                                                                                                        |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [ContentSaliencyConditionComplexityScore](yarn.node.contentsaliencyconditioncomplexityscore.md) | Gets the content saliency condition complexity score for this node.                                                                                                |
| [ContentSaliencyConditionVariables](yarn.node.contentsaliencyconditionvariables.md)             | Gets an enumerable containing the names of variables that must be evaluated in order to determine whether this node can be selected as a piece of salient content. |
| [Headers](yarn.node.headers.md)                                                                 | The headers present on this node.                                                                                                                                  |
| [Instructions](yarn.node.instructions.md)                                                       | The list of instructions in this node.                                                                                                                             |
| [IsNodeGroupHub](yarn.node.isnodegrouphub.md)                                                   | Gets a value indicating whether this node is the 'hub' node for a node group.                                                                                      |
| [Name](yarn.node.name.md)                                                                       | The name of this node.                                                                                                                                             |
| [NodeGroup](yarn.node.nodegroup.md)                                                             | Gets the name of the node group that this node is a part of, or `null` if it is not part of a node group.                                                          |
| [Tags](yarn.node.tags.md)                                                                       | Gets the collection of tags defined for this node, if any. If no tags are defined, returns an empty collection.                                                    |
| [TrackingVariableName](yarn.node.trackingvariablename.md)                                       | Gets the name of the variable used for tracking the number of times this node has completed, or `null` if this node is not tracked.                                |
