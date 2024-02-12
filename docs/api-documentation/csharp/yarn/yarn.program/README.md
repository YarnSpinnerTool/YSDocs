# Program

Class in [Yarn](../)

Inherits from `System.Object`

## Summary

A compiled Yarn program.

```csharp
public class Program
```

## Methods

| Name                                                     | Description                                                               |
| -------------------------------------------------------- | ------------------------------------------------------------------------- |
| [Combine(Program\[\])](yarn.program.combine.md)          | Creates a new Program by merging multiple Programs together.              |
| [LineIDsForNode(string)](yarn.program.lineidsfornode.md) | Identifies and returns a list of all line and option IDs inside the node. |
| [ToString()](yarn.program.tostring.md)                   |                                                                           |

## Properties

| Name                                           | Description                                                                                                                                                |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [InitialValues](yarn.program.initialvalues.md) | The collection of initial values for variables; if a PUSH\_VARIABLE instruction is run, and the value is not found in the storage, this value will be used |
| [Name](yarn.program.name.md)                   | The name of the program.                                                                                                                                   |
| [Nodes](yarn.program.nodes.md)                 | The collection of nodes in this program.                                                                                                                   |
