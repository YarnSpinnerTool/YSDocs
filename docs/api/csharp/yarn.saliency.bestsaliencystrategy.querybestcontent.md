# QueryBestContent(IEnumerable\<ContentSaliencyOption>)

Method in [BestSaliencyStrategy](yarn.saliency.bestsaliencystrategy.md)

## Summary

Chooses an item from content that is the most appropriate (o&#x72;_&#x73;alient_ ) for the user's current context.

```csharp
public ContentSaliencyOption? QueryBestContent(IEnumerable<ContentSaliencyOption> content)
```

## Remarks

Implementations of this method should not modify any state

* that is, they should be 'read-only' operations. If a strategy\
  needs to record information about when a piece of content has been\
  selected, it should do it in the [ContentWasSelected(ContentSaliencyOption)](yarn.saliency.icontentsaliencystrategy.contentwasselected.md)\
  method.

## Parameters

| Name                                                                                  | Description                                                  |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| `System.Collections.Generic.IEnumerable<Yarn.Saliency.ContentSaliencyOption>` content | A collection of content items. This collection may be empty. |

## Returns

An item from `content` that is the most\
appropriate for display, or `null` if no content\
should be displayed.
