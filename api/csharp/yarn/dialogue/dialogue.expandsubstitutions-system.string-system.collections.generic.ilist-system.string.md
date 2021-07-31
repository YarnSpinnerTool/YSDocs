# ExpandSubstitutions\(String, IList&lt;String&gt;\)

Replaces all substitution markers in a text with the given substitution list.

```csharp
public static string ExpandSubstitutions(string text, IList<string> substitutions)
```

## Remarks

This method replaces substitution markers - for example, `{0}`

* with the corresponding entry in `substitutions`. If `text` contains a

  substitution marker whose index is not present in `substitutions`, it is ignored.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) text | The text containing substitution markers. |
| [`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IList{System.String}) substitutions | The list of substitutions. |

## Return Type

[`string`](https://docs.microsoft.com/dotnet/api/System.String): `text`, with the content from `substitutions` inserted.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L896), line 896.

