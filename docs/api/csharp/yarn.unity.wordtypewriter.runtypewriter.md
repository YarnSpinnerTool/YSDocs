# WordTypewriter.RunTypewriter(Markup.MarkupParseResult,CancellationToken)

Method in [WordTypewriter](/docs/api/csharp/yarn.unity.wordtypewriter.md)

## Summary


Displays the contents of a line over time.


```csharp
public async YarnTask RunTypewriter(Markup.MarkupParseResult line, CancellationToken cancellationToken)
```

## Remarks

<p>This method is called when a dialogue presenter wants to
deliver a line's text. The typewriter should present the text to the
user; it may take as long as it needs to do so. </p> <p>If <code>cancellationToken</code>'s <code>System.Threading.CancellationToken.IsCancellationRequested</code> becomes true, the
typewriter effect should end early and present the entire contents
of <code>line</code>.</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md) line|The line to display.|
|`System.Threading.CancellationToken` cancellationToken|A token that indicates that the typewriter effect should be cancelled.|

## Returns

A task that completes when the typewriter effect has
finished.

