# ExtractStringBlocks(IEnumerable\<Node>,ProjectDebugInfo)

Method in [Utility](yarn.compiler.utility.md)

## Summary

Gets the collection of contiguous runs of lines in the provided\
nodes. Each run of lines is guaranteed to run to completion once\
entered.

```csharp
public static List<List<string>> ExtractStringBlocks(IEnumerable<Node> nodes, ProjectDebugInfo projectDebugInfo)
```

## Parameters

| Name                                                                                 | Description                                                 |
| ------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| `System.Collections.Generic.IEnumerable<Yarn.Node>` nodes                            | The nodes to get string blocks for.                         |
| [Yarn.Compiler.ProjectDebugInfo](yarn.compiler.projectdebuginfo.md) projectDebugInfo | An object containing debugging information for the project. |

## Returns

A collection of runs of lines.
