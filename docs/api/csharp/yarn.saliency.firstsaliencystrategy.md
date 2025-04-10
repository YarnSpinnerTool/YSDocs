# FirstSaliencyStrategy

Class in [Yarn.Saliency](yarn.saliency.md)

Inherits from `System.Object`

## Summary

A content saliency strategy that always returns the first non-failing item in the list of available options.

```csharp
public class FirstSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks

This saliency strategy is used when a [Dialogue](yarn.dialogue.md) has no provided saliency strategy, but is required to make a decision.

## Methods

| Name                                                                                                   | Description                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.firstsaliencystrategy.contentwasselected.md) | Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content. |
| [QueryBestContent(IEnumerable)](yarn.saliency.firstsaliencystrategy.querybestcontent.md)               | Chooses an item from content that is the most appropriate (or _salient_ ) for the user's current context.                                                        |
