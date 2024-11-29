# BestLeastRecentlyViewedSalienceStrategy

Class in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

Inherits from `System.Object`

## Summary


A content saliency strategy that returns the first of the best,
least-recently seen choices from the provided options.


```csharp
public class BestLeastRecentlyViewedSalienceStrategy : IContentSaliencyStrategy
```

## Remarks


This strategy stores information about the number of times each piece of
content has been seen in the provided  <code>Yarn.Saliency.BestLeastRecentlyViewedSalienceStrategy.VariableStorage</code> .


## Constructors

|Name|Description|
|:---|:---|
|[BestLeastRecentlyViewedSalienceStrategy(IVariableStorage)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencestrategy..ctor.md)|Initalises a new instance of the  <a href="yarn.saliency.bestleastrecentlyviewedsaliencestrategy.md">BestLeastRecentlyViewedSalienceStrategy</a>  class.|

## Methods

|Name|Description|
|:---|:---|
|[ContentWasSelected(ContentSaliencyOption)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencestrategy.contentwasselected.md)|Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content.|
|[QueryBestContent(IEnumerable<ContentSaliencyOption>)](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencestrategy.querybestcontent.md)|Chooses an item from content that is the most appropriate (or <i>salient</i> ) for the user's current context.|

