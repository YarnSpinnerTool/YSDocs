# Dialogue.GetSaliencyOptionsForNodeGroup(string)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Queries the  <a href="yarn.dialogue.md">Dialogue</a>  for what content could possibly
run if the node group nodeGroup was run.


```csharp
public IEnumerable<Saliency.ContentSaliencyOption> GetSaliencyOptionsForNodeGroup(string nodeGroup)
```

## Remarks

<p>This method evaluates all nodes in the given node group, and
returns a <a href="yarn.saliency.contentsaliencyoption.md">ContentSaliencyOption</a> object for
each node. This object contains the current number of passing and
failing 'when' clauses on the node, as well as the complexity score
for that node. This is the same information that's passed to a <a href="yarn.saliency.icontentsaliencystrategy.md">IContentSaliencyStrategy</a> object's <a href="yarn.saliency.icontentsaliencystrategy.querybestcontent.md">QueryBestContent(IEnumerable&lt;ContentSaliencyOption&gt;)</a>
method. This method is read-only, and calling it will not modify any
variable state.
</p> <p>Note that this method does not filter its output, and may
include content options whose <a href="yarn.saliency.contentsaliencyoption.failingconditionvaluecount.md">FailingConditionValueCount</a>
is greater than zero. It's up to the caller of this function to
filter out these options if they're not wanted.</p> <p>
This method can be used to see if <em>any</em> content will appear
when a given node group is run. If the collection returned by this
method is empty, then running this node group will not result in any
content. This can be used, for example, to decide whether to show a
'character can be spoken to' indicator. You can also examine the
individal <a href="yarn.saliency.contentsaliencyoption.md">ContentSaliencyOption</a> objects to
see if any content is available that passes a filter, such as
whether content might appear that has a user-defined 'plot critical'
tag.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeGroup|The name of the node group to get available content for.|

## Returns

A collection of  <a href="yarn.saliency.contentsaliencyoption.md">ContentSaliencyOption</a>  objects that may appear if
and when the node group  <code>nodeGroup</code>  is run.


