# BestLeastRecentlyViewedSaliencyStrategy

Class in [Yarn.Saliency](yarn.saliency.md)

Inherits from `System.Object`

## Summary

A content saliency strategy that returns the first of the best,\
least-recently seen choices from the provided options.

```csharp
public class BestLeastRecentlyViewedSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks

This strategy stores information about the number of times each piece of\
content has been seen in the provided `Yarn.Saliency.BestLeastRecentlyViewedSaliencyStrategy.VariableStorage` .

## Constructors

| Name                                                                                                                        | Description                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| [BestLeastRecentlyViewedSaliencyStrategy(IVariableStorage)](yarn.saliency.bestleastrecentlyviewedsaliencystrategy..ctor.md) | Initalises a new instance of the [BestLeastRecentlyViewedSaliencyStrategy](yarn.saliency.bestleastrecentlyviewedsaliencystrategy.md) class. |

## Methods

| Name                                                                                                                     | Description                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.bestleastrecentlyviewedsaliencystrategy.contentwasselected.md) | Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content. |
| [QueryBestContent(IEnumerable)](yarn.saliency.bestleastrecentlyviewedsaliencystrategy.querybestcontent.md)               | Chooses an item from content that is the most appropriate (or _salient_ ) for the user's current context.                                                        |
