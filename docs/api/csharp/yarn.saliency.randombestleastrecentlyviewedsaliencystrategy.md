# RandomBestLeastRecentlyViewedSaliencyStrategy

Class in [Yarn.Saliency](yarn.saliency.md)

Inherits from `System.Object`

## Summary

A content saliency strategy that returns a random choice of the best,\
least-recently seen choices from the provided options.

```csharp
public class RandomBestLeastRecentlyViewedSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks

This strategy stores information about the number of times each piece of\
content has been seen in the provided `Yarn.Saliency.RandomBestLeastRecentlyViewedSaliencyStrategy.VariableStorage` .

## Constructors

| Name                                                                                                                                    | Description                                                                                                                                              |
| --------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [RandomBestLeastRecentlyViewedSaliencyStrategy(IVariableStorage)](yarn.saliency.randombestleastrecentlyviewedsaliencystrategy..ctor.md) | Initializes a new instance of the [RandomBestLeastRecentlyViewedSaliencyStrategy](yarn.saliency.randombestleastrecentlyviewedsaliencystrategy.md) class. |

## Methods

| Name                                                                                                                           | Description                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.randombestleastrecentlyviewedsaliencystrategy.contentwasselected.md) | Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content. |
| [QueryBestContent(IEnumerable)](yarn.saliency.randombestleastrecentlyviewedsaliencystrategy.querybestcontent.md)               | Chooses an item from content that is the most appropriate (or _salient_ ) for the user's current context.                                                        |
