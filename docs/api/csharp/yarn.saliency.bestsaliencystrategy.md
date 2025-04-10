# BestSaliencyStrategy

Class in [Yarn.Saliency](yarn.saliency.md)

Inherits from `System.Object`

## Summary

A content saliency strategy that returns the best of the provided options.

```csharp
public class BestSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks

This strategy always selects the single best of the available items, regardless of how many times it has been seen before. For a saliency strategy that takes into account how recently content has been seen, see [BestLeastRecentlyViewedSalienceStrategy](yarn.saliency.bestleastrecentlyviewedsaliencestrategy.md) .

## Methods

| Name                                                                                                  | Description                                                                                                                                                      |
| ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.bestsaliencystrategy.contentwasselected.md) | Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content. |
| [QueryBestContent(IEnumerable)](yarn.saliency.bestsaliencystrategy.querybestcontent.md)               | Chooses an item from content that is the most appropriate (or _salient_ ) for the user's current context.                                                        |
