# WordTypewriter

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


An implementation of  <a href="yarn.unity.iasynctypewriter.md">IAsyncTypewriter</a>  that delivers
words one at a time, and invokes any  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a> s along the way as needed.


```csharp
public class WordTypewriter : IAsyncTypewriter
```

## Methods

|Name|Description|
|:---|:---|
|[ContentWillDismiss()](/docs/api/csharp/yarn.unity.wordtypewriter.contentwilldismiss.md)||
|[PrepareForContent(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.wordtypewriter.prepareforcontent.md)||
|[RunTypewriter(Markup.MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.wordtypewriter.runtypewriter.md)|Displays the contents of a line over time.|

## Properties

|Name|Description|
|:---|:---|
|[ActionMarkupHandlers](/docs/api/csharp/yarn.unity.wordtypewriter.actionmarkuphandlers.md)|A collection of  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  objects that should be invoked as needed during the typewriter's delivery in  <a href="yarn.unity.wordtypewriter.runtypewriter.md">RunTypewriter(Markup.MarkupParseResult,CancellationToken)</a> , depending upon the contents of a line.|
|[Text](/docs/api/csharp/yarn.unity.wordtypewriter.text.md)|The  <code>TMPro.TMP_Text</code>  to display the text in.|
|[WordsPerSecond](/docs/api/csharp/yarn.unity.wordtypewriter.wordspersecond.md)|The number of words per second to deliver.|

