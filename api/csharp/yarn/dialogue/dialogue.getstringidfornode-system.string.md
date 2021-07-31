# GetStringIDForNode\(String\)

Returns the string ID that contains the original, uncompiled source text for a node.

```csharp
public string GetStringIDForNode(string nodeName)
```

## Remarks

A node's source text will only be present in the string table if its `tags` header contains `rawText`.

Because the [`Dialogue`](./) class is designed to be unaware of the contents of the string table, this method does not test to see if the string table contains an entry with the line ID. You will need to test for that yourself.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) nodeName | The name of the node. |

## Return Type

[`string`](https://docs.microsoft.com/dotnet/api/System.String): The string ID.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L768), line 768.

