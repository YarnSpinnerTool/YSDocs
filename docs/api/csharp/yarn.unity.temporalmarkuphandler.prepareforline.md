# PrepareForLine(MarkupParseResult,TMP\_Text)

Method in [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md)

## Summary

Called when the line view receives the line, to prepare for showing the line.

```csharp
public abstract void PrepareForLine(MarkupParseResult line, TMP_Text text);
```

## Remarks

This method is called before any part of the line is visible, and is an opportunity to set up any part of the [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) 's display before the user can see it.

## Parameters

| Name                                                                   | Description                                                    |
| ---------------------------------------------------------------------- | -------------------------------------------------------------- |
| [Yarn.Markup.MarkupParseResult](yarn.markup.markupparseresult.md) line | The line being presented.                                      |
| `TMPro.TMP_Text` text                                                  | A `TMPro.TMP_Text` object that the line is being displayed in. |
