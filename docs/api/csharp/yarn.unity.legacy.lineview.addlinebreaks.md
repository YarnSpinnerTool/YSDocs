# AddLineBreaks(Markup.MarkupParseResult)

Method in [LineView](yarn.unity.legacy.lineview.md)

## Summary

Inserts TextMeshPro line break markup in a line where Yarn line\
break attributes appear.

```csharp
public static string AddLineBreaks(Markup.MarkupParseResult line)
```

## Parameters

| Name                                                                   | Description                                     |
| ---------------------------------------------------------------------- | ----------------------------------------------- |
| [Yarn.Markup.MarkupParseResult](yarn.markup.markupparseresult.md) line | The line containing Yarn line break attributes. |

## Returns

A string containing TextMeshPro `<br/>` markers\
where Yarn `[br/]` attributes appear.
