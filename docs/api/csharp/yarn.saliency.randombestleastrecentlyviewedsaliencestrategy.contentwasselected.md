# RandomBestLeastRecentlyViewedSalienceStrategy.ContentWasSelected(ContentSaliencyOption)

Method in [RandomBestLeastRecentlyViewedSalienceStrategy](/docs/api/csharp/yarn.saliency.randombestleastrecentlyviewedsaliencestrategy.md)

## Summary


Called by Yarn Spinner to indicate that a piece of salient content
has been selected, and this system should update any state related
to how it selects content.


```csharp
public void ContentWasSelected(ContentSaliencyOption content)
```

## Remarks

If a content saliency strategy does not need to keep track
of any state, then this method can be empty.

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Saliency.ContentSaliencyOption](/docs/api/csharp/yarn.saliency.contentsaliencyoption.md) content|The content that has been selected.|
