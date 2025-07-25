# GetStringIDForNode(string)

Method in [Dialogue](yarn.dialogue.md)

## Summary

Returns the string ID that contains the original, uncompiled source\
text for a node.

```csharp
public string? GetStringIDForNode(string nodeName)
```

## Remarks

A node's source text will only be present in the string table if its`tags` header contains `rawText`.

Because the [Dialogue](yarn.dialogue.md) class is designed to be unaware\
of the contents of the string table, this method does not test to\
see if the string table contains an entry with the line ID. You will\
need to test for that yourself.

## Parameters

| Name              | Description           |
| ----------------- | --------------------- |
| `string` nodeName | The name of the node. |

## Returns

The string ID.
