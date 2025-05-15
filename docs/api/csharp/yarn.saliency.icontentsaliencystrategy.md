# IContentSaliencyStrategy

Interface in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

## Summary


Contains methods for choosing a piece of content from a collection of
options.


```csharp
public interface IContentSaliencyStrategy
```

## Methods

|Name|Description|
|:---|:---|
|[ContentWasSelected(ContentSaliencyOption)](/docs/api/csharp/yarn.saliency.icontentsaliencystrategy.contentwasselected.md)|Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content.|
|[QueryBestContent(IEnumerable<ContentSaliencyOption>)](/docs/api/csharp/yarn.saliency.icontentsaliencystrategy.querybestcontent.md)|Chooses an item from content that is the most appropriate (or <i>salient</i> ) for the user's current context.|

