# DetermineNodeConnections(string\[])

Method in [Utility](./)

## Summary

Finds and collates every jump in every node.

```csharp
public static List<List<GraphingNode>> DetermineNodeConnections(string[] YarnFileContents)
```

## Parameters

| Name                        | Description                                           |
| --------------------------- | ----------------------------------------------------- |
| `string[]` YarnFileContents | The collection of yarn file content to parse and walk |

## Returns

A list of lists of GraphingNode each containing a node, its jumps, and any positional info.
