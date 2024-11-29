# RandomBestLeastRecentlyViewedSalienceStrategy

Class in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

Inherits from `System.Object`

## Summary


A content saliency strategy that returns a random choice of the best,
least-recently seen choices from the provided options.


```csharp
public class RandomBestLeastRecentlyViewedSalienceStrategy : IContentSaliencyStrategy
```

## Remarks


This strategy stores information about the number of times each piece of
content has been seen in the provided  <code>Yarn.Saliency.RandomBestLeastRecentlyViewedSalienceStrategy.VariableStorage</code> .


## Constructors

|Name|Description|
|:---|:---|
|[RandomBestLeastRecentlyViewedSalienceStrategy(IVariableStorage)](/docs/api/csharp/yarn.saliency.randombestleastrecentlyviewedsaliencestrategy..ctor.md)|Initializes a new instance of the  <a href="yarn.saliency.randombestleastrecentlyviewedsaliencestrategy.md">RandomBestLeastRecentlyViewedSalienceStrategy</a>  class.|

## Methods

|Name|Description|
|:---|:---|
|[ContentWasSelected(ContentSaliencyOption)](/docs/api/csharp/yarn.saliency.randombestleastrecentlyviewedsaliencestrategy.contentwasselected.md)|Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content.|
|[QueryBestContent(IEnumerable<ContentSaliencyOption>)](/docs/api/csharp/yarn.saliency.randombestleastrecentlyviewedsaliencestrategy.querybestcontent.md)|Chooses an item from content that is the most appropriate (or <i>salient</i> ) for the user's current context.|

