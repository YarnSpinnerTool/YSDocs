# GetTagsForNode(string)

Method in [Dialogue](yarn.dialogue.md)

{% hint style="warning" %}
This method is obsolete and may be removed from a future version of Yarn Spinner: Use GetHeaderValue(nodeName, "tags"), and split the result by spaces.
{% endhint %}

## Summary

Returns the tags for the node `nodeName` .

```csharp
public IEnumerable<string> GetTagsForNode(string nodeName)
```

## Remarks

The tags for a node are defined by setting the `tags` header in\
the node's source code. This header must be a space-separated list.

## Parameters

| Name              | Description           |
| ----------------- | --------------------- |
| `string` nodeName | The name of the node. |

## Returns

The node's tags, or `null` if the node is\
not present in the Program.
