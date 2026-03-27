# IAsyncTypewriter

Interface in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

## Summary


An object that can handle delivery of a line's text over time.


```csharp
public interface IAsyncTypewriter
```

## Methods

|Name|Description|
|:---|:---|
|[ContentDidDismiss()](/docs/api/csharp/yarn.unity.iasynctypewriter.contentdiddismiss.md)|Called after the content has been visibly hidden.|
|[ContentWillDismiss()](/docs/api/csharp/yarn.unity.iasynctypewriter.contentwilldismiss.md)|Called right before the content will be visibly hidden|
|[PrepareForContent(Markup.MarkupParseResult)](/docs/api/csharp/yarn.unity.iasynctypewriter.prepareforcontent.md)|Called by the presenter before content has been shown. This gives the typewriter it's chance to do any setup before the content is visibly shown.|
|[RunTypewriter(Markup.MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.iasynctypewriter.runtypewriter.md)|Displays the contents of a line over time.|

## Properties

|Name|Description|
|:---|:---|
|[ActionMarkupHandlers](/docs/api/csharp/yarn.unity.iasynctypewriter.actionmarkuphandlers.md)|The list of action markup handlers that this typewriter should call out to while typewriting.|
|[TextElement](/docs/api/csharp/yarn.unity.iasynctypewriter.textelement.md)|The main text element that the presenter intends the typewriter to work with|

