# GetSaliencyOptionsForNodeGroup(string)

Method in [Dialogue](yarn.dialogue.md)

## Summary

Queries the [Dialogue](yarn.dialogue.md) for what content could possibly run if the node group nodeGroup was run.

```csharp
public IEnumerable<Saliency.ContentSaliencyOption> GetSaliencyOptionsForNodeGroup(string nodeGroup)
```

## Remarks

This method evaluates all nodes in the given node group, and returns a [ContentSaliencyOption](yarn.saliency.contentsaliencyoption.md) object for each node. This object contains the current number of passing and failing 'when' clauses on the node, as well as the complexity score for that node. This is the same information that's passed to a [IContentSaliencyStrategy](yarn.saliency.icontentsaliencystrategy.md) object's [QueryBestContent(IEnumerable\<ContentSaliencyOption>)](yarn.saliency.icontentsaliencystrategy.querybestcontent.md) method. This method is read-only, and calling it will not modify any variable state.

Note that this method does not filter its output, and may include content options whose [FailingConditionValueCount](yarn.saliency.contentsaliencyoption.failingconditionvaluecount.md) is greater than zero. It's up to the caller of this function to filter out these options if they're not wanted.

This method can be used to see if _any_ content will appear when a given node group is run. If the collection returned by this method is empty, then running this node group will not result in any content. This can be used, for example, to decide whether to show a 'character can be spoken to' indicator. You can also examine the individal [ContentSaliencyOption](yarn.saliency.contentsaliencyoption.md) objects to see if any content is available that passes a filter, such as whether content might appear that has a user-defined 'plot critical' tag.

## Parameters

| Name               | Description                                              |
| ------------------ | -------------------------------------------------------- |
| `string` nodeGroup | The name of the node group to get available content for. |

## Returns

A collection of [ContentSaliencyOption](yarn.saliency.contentsaliencyoption.md) objects that may appear if and when the node group `nodeGroup` is run.
