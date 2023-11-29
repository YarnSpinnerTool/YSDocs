# Dialogue.GetStringIDForNode(string)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Returns the string ID that contains the original, uncompiled source
text for a node.


```csharp
public string GetStringIDForNode(string nodeName)
```

## Remarks

<p>
A node's source text will only be present in the string table if its
<code>tags</code> header contains <code>rawText</code>.
</p> <p>
Because the <a href="yarn.dialogue.md">Dialogue</a> class is designed to be unaware
of the contents of the string table, this method does not test to
see if the string table contains an entry with the line ID. You will
need to test for that yourself.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName|The name of the node.|

## Returns

The string ID.

