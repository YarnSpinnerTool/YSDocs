# LineIDsForNode(string)

Method in [Program](./)

## Summary

Identifies and returns a list of all line and option IDs inside the node.

```csharp
public List<string> LineIDsForNode(string nodeName)
```

## Parameters

| Name              | Description                                   |
| ----------------- | --------------------------------------------- |
| `string` nodeName | The name of the node whos line IDs you covet. |

## Returns

The line IDs of all lines and options inside the node, or null if `nodeName` doesn't exist in the program.
