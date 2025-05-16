---
description: Learn how to implement a custom saliency strategy for your narratives.
---

# Custom Saliency Strategies

Yarn Spinner 3 introduced a new system for selecting which content should be presented next, called Saliency Strategies. Whenever it's time to select the next piece of salient content from node groups or line groups, Yarn Spinner consults its saliency strategy to determine which piece should be chosen.

This guide explores an implementation provided in our **Custom Saliency Strategies** Sample.

{% include "../../.gitbook/includes/you-can-learn-how-to-add-th....md" %}

While we provide several built-in saliency strategies that cover common scenarios, we can't anticipate every possible need. That's where custom strategies come in, which is the focus of this sample. We'll demonstrate how to create a new custom saliency strategy to meet specific requirements.

{% hint style="info" %}
This sample focuses on creating custom saliency strategies, not on saliency itself. For more information about the concept of saliency, see [storylets-and-saliency-a-primer.md](../../write-yarn-scripts/advanced-scripting/storylets-and-saliency-a-primer.md "mention"), and [saliency.md](../../write-yarn-scripts/advanced-scripting/saliency.md "mention").
{% endhint %}

### What we'll be covering

* Creating new saliency strategies through the `IContentSaliencyStrategy` interface
* Reading line metadata
* Reading node headers

### IContentSaliencyStrategy

The `IContentSaliencyStrategy` interface requires implementing just two methods: `QueryBestContent` and `ContentWasSelected`.

* `QueryBestContent`: Called when Yarn Spinner asks, "If I were to run this block of content, what would be selected?"
* `ContentWasSelected`: Called when Yarn Spinner informs the strategy, "This specific piece has been chosen"

When Yarn Spinner needs to select a piece of salient content, it first asks its strategy what content would be selected (`QueryBestContent`) and then selects it and informs the strategy of this selection (`ContentWasSelected`).

You might wonder why this functionality is split into two methods, especially when the first call is often immediately followed by the second. For many saliency strategies, it won't matter - querying and selecting can effectively be the same operation, with the only required state being the list of content to analyze.

However, other strategies require maintaining state that would be affected if selection and querying were combined. For example, the built-in "Best Least Recently Viewed" strategy tracks which content it has shown previously to avoid showing the same piece of content twice in a row. Each time it selects content, it marks it as seen, which deprioritizes that specific content for future selections.

This design creates a clear separation: `QueryBestContent` is non-mutating, while `ContentWasSelected` can modify state. The alternative would be to prevent querying available content altogether, but this would be too limiting - it would prevent you from checking whether content is available, which might be useful for showing indicators that an NPC has something to say.

### Weighted Saliency

The sample includes a custom saliency strategy in `WeightedSaliencySelector.cs`. This strategy assigns a custom weight to each storylet, as specified by the writer, and uses these weights to determine the probability of each storylet being shown.

Each piece of salient content is given a range proportional to its weight, and then one is chosen randomly from the combined range of all weights. In practical terms, given the following line group:

```
=> I am line A #weight:2
=> I am line B #weight:1
```

"I am line A" will be shown approximately two-thirds of the time, while "I am line B" will appear approximately one-third of the time.

When asked for the best content, the strategy first filters out any content with failing conditions. After this filtering, we're left with content where all conditions (line conditions or when headers) have evaluated to true. The next step is to determine the weighting for each piece of content.

Our weighted saliency strategy supports both line groups and node groups, which require slightly different approaches:

For node groups, we look for the `weight` header in the node headers:

```csharp
weightString = runner.Dialogue.GetHeaderValue(element.ContentID, WeightKey)
```

For line groups, we look for the `weight` tag in the metadata:

```csharp
var lineKey = WeightKey + ':';
foreach (var metadata in runner.YarnProject.lineMetadata.GetMetadata(element.ContentID))
{
    if (metadata.StartsWith(lineKey))
    {
        weightString = metadata.Substring(lineKey.Length).Trim();
        break;
    }
}
```

Once we have the string values for weights, we convert them to integers. If the conversion fails, or if there isn't a weight value in the headers or metadata, we assign a default weight of one.

With the weights established, we build a list of ranges representing those weights. Finally, we generate a random number within the combined size of all ranges and use that to select which content to present.

{% hint style="info" %}
You'll notice several `return null` statements in this method, which is entirely appropriate. It's normal and expected that sometimes there won't be any valid content to run. Returning null is how you inform Yarn Spinner that no valid content is available.
{% endhint %}
