# TemporalMarkupHandler.PrepareForLine(MarkupParseResult,TMP_Text)

Method in [TemporalMarkupHandler](/docs/api/csharp/yarn.unity.temporalmarkuphandler.md)

## Summary


Called when the line view receives the line, to prepare for showing
the line.


```csharp
public abstract void PrepareForLine(MarkupParseResult line, TMP_Text text);
```

## Remarks


This method is called before any part of the line is visible, and is
an opportunity to set up any part of the  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a> 's display before the user can see it.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md) line|The line being presented.|
|`TMPro.TMP_Text` text|A  <code>TMPro.TMP_Text</code>  object that the line is being displayed in.|

