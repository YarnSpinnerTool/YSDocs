# FirstSaliencyStrategy

Class in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

Inherits from `System.Object`

## Summary


A content saliency strategy that always returns the first non-failing
item in the list of available options.


```csharp
public class FirstSaliencyStrategy : IContentSaliencyStrategy
```

## Remarks


This saliency strategy is used when a  <a href="yarn.dialogue.md">Dialogue</a>  has no
provided saliency strategy, but is required to make a decision.


## Methods

|Name|Description|
|:---|:---|
|[ContentWasSelected(ContentSaliencyOption)](/docs/api/csharp/yarn.saliency.firstsaliencystrategy.contentwasselected.md)|Called by Yarn Spinner to indicate that a piece of salient content has been selected, and this system should update any state related to how it selects content.|
|[QueryBestContent(IEnumerable<ContentSaliencyOption>)](/docs/api/csharp/yarn.saliency.firstsaliencystrategy.querybestcontent.md)|Chooses an item from content that is the most appropriate (or <i>salient</i> ) for the user's current context.|

