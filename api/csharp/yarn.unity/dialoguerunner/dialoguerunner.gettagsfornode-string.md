# GetTagsForNode\(String\)

Returns the collection of tags that the node associated with the node named `nodeName`.

```csharp
public IEnumerable<string> GetTagsForNode(String nodeName)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| `String` nodeName | The name of the node. |

## Return Type

`IEnumerable<String>`: The collection of tags associated with the node, or `null` if no node with that name exists.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L355), line 355.

