# Dialogue.GetTagsForNode(string)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

{% hint style="warning" %}
This method is <b>obsolete</b> and may be removed from a future version of Yarn Spinner: Use GetHeaderValue(nodeName, "tags"), and split the result by spaces.
{% endhint %}

## Summary


Returns the tags for the node  <code>nodeName</code> .


```csharp
public IEnumerable<string> GetTagsForNode(string nodeName)
```

## Remarks


The tags for a node are defined by setting the  <code>tags</code>  header in
the node's source code. This header must be a space-separated list.


## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName|The name of the node.|

## Returns

The node's tags, or  <code>null</code>  if the node is
not present in the Program.

