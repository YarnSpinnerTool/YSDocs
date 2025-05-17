# BestLeastRecentlyViewedSaliencyStrategy

Class in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

Inherits from `System.Object`

## Summary


A content saliency strategy that returns the first of the best,
least-recently seen choices from the provided options.


```csharp
public class BestLeastRecentlyViewedSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks


This strategy stores information about the number of times each piece of
content has been seen in the provided  `Yarn.Saliency.BestLeastRecentlyViewedSaliencyStrategy.VariableStorage` .


## Constructors

|Name|Description|
|:---|:---|
|[BestLeastRecentlyViewedSaliencyStrategy(IVariableStorage)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencystrategy..ctor.md)|Initalises a new instance of the  <a href="yarn.saliency.bestleastrecentlyviewedsaliencystrategy.md">BestLeastRecentlyViewedSaliencyStrategy</a>  class.|

## Methods

|Name|Description|
|:---|:---|
|[ContentWasSelected(ContentSaliencyOption)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencystrategy.contentwasselected.md)|Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content.|
|[QueryBestContent(IEnumerable<ContentSaliencyOption>)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencystrategy.querybestcontent.md)|Chooses an item from content that is the most appropriate (or <i>salient</i> ) for the user's current context.|

