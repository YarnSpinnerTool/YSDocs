# OnLineTextWillAppear(MarkupParseResult,TMP\_Text)

Method in [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md)

## Summary

Called immediately before the first character in the line is presented.

```csharp
public abstract void OnLineTextWillAppear(MarkupParseResult line, TMP_Text text);
```

## Parameters

| Name                                                                   | Description                                                    |
| ---------------------------------------------------------------------- | -------------------------------------------------------------- |
| [Yarn.Markup.MarkupParseResult](yarn.markup.markupparseresult.md) line | The line being presented.                                      |
| `TMPro.TMP_Text` text                                                  | A `TMPro.TMP_Text` object that the line is being displayed in. |
