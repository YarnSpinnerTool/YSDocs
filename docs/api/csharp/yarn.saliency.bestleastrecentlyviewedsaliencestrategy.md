# BestLeastRecentlyViewedSalienceStrategy

Class in [Yarn.Saliency](yarn.saliency.md)

Inherits from `System.Object`

## Summary

A content saliency strategy that returns the first of the best, least-recently seen choices from the provided options.

```csharp
public class BestLeastRecentlyViewedSalienceStrategy : IContentSaliencyStrategy
```

## Remarks

This strategy stores information about the number of times each piece of content has been seen in the provided `Yarn.Saliency.BestLeastRecentlyViewedSalienceStrategy.VariableStorage` .

## Constructors

| Name                                                                                                                        | Description                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| [BestLeastRecentlyViewedSalienceStrategy(IVariableStorage)](yarn.saliency.bestleastrecentlyviewedsaliencestrategy..ctor.md) | Initalises a new instance of the [BestLeastRecentlyViewedSalienceStrategy](yarn.saliency.bestleastrecentlyviewedsaliencestrategy.md) class. |

## Methods

| Name                                                                                                                     | Description                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.bestleastrecentlyviewedsaliencestrategy.contentwasselected.md) | Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content. |
| [QueryBestContent(IEnumerable)](yarn.saliency.bestleastrecentlyviewedsaliencestrategy.querybestcontent.md)               | Chooses an item from content that is the most appropriate (or _salient_ ) for the user's current context.                                                        |
