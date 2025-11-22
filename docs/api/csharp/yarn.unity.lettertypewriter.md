# LetterTypewriter

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


An implementation of  <a href="yarn.unity.iasynctypewriter.md">IAsyncTypewriter</a>  that delivers
characters one at a time, and invokes any  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a> s along the way as needed.


```csharp
public class LetterTypewriter : IAsyncTypewriter
```

## Methods

|Name|Description|
|:---|:---|
|[ContentWillDismiss()](/docs/api/csharp/yarn.unity.lettertypewriter.contentwilldismiss.md)||
|[PrepareForContent(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.lettertypewriter.prepareforcontent.md)||
|[RunTypewriter(Markup.MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.lettertypewriter.runtypewriter.md)|Displays the contents of a line over time.|

## Properties

|Name|Description|
|:---|:---|
|[ActionMarkupHandlers](/docs/api/csharp/yarn.unity.lettertypewriter.actionmarkuphandlers.md)|A collection of  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  objects that should be invoked as needed during the typewriter's delivery in  <a href="yarn.unity.lettertypewriter.runtypewriter.md">RunTypewriter(Markup.MarkupParseResult,CancellationToken)</a> , depending upon the contents of a line.|
|[CharactersPerSecond](/docs/api/csharp/yarn.unity.lettertypewriter.characterspersecond.md)|The number of characters per second to deliver.|
|[Text](/docs/api/csharp/yarn.unity.lettertypewriter.text.md)|The  <code>TMPro.TMP_Text</code>  to display the text in.|

