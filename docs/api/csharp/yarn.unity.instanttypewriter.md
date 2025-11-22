# InstantTypewriter

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


An implementation of  <a href="yarn.unity.iasynctypewriter.md">IAsyncTypewriter</a>  that delivers
all content instantly, and invokes any  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a> s along the way as needed.


```csharp
public class InstantTypewriter : IAsyncTypewriter
```

## Methods

|Name|Description|
|:---|:---|
|[ContentWillDismiss()](/docs/api/csharp/yarn.unity.instanttypewriter.contentwilldismiss.md)||
|[PrepareForContent(MarkupParseResult)](/docs/api/csharp/yarn.unity.instanttypewriter.prepareforcontent.md)||
|[RunTypewriter(Markup.MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.instanttypewriter.runtypewriter.md)|Displays the contents of a line over time.|

## Properties

|Name|Description|
|:---|:---|
|[ActionMarkupHandlers](/docs/api/csharp/yarn.unity.instanttypewriter.actionmarkuphandlers.md)|A collection of  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  objects that should be invoked as needed during the typewriter's delivery in  <a href="yarn.unity.instanttypewriter.runtypewriter.md">RunTypewriter(Markup.MarkupParseResult,CancellationToken)</a> , depending upon the contents of a line.|
|[Text](/docs/api/csharp/yarn.unity.instanttypewriter.text.md)|The  <code>TMPro.TMP_Text</code>  to display the text in.|

