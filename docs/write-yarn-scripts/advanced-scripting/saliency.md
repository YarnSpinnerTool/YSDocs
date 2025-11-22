---
description: >-
  Learn about saliency and saliency strategies, which let you control how line
  groups and node groups select which content to run.
icon: ticket-perforated
---

# Saliency

In Yarn Spinner, **saliency** lets you control how [line groups](../scripting-fundamentals/line-groups.md) and [node groups](node-groups.md) select which content to run.

{% hint style="warning" %}
We recommend you read the [storylets-and-saliency-a-primer.md](storylets-and-saliency-a-primer.md "mention") before reading this page.&#x20;
{% endhint %}

When a line group or node group needs to run content, it needs to make a decision about which item in the group to choose. The method for making this decision is called a _saliency strategy_.

Saliency strategies are provided with the following information about each item:

* How many of its conditions passed (that is, the `when:` clauses on a node group, or the single condition on a line group)
* How many of its conditions failed
* The total complexity of all of its conditions:
  * The `always` condition has a complexity of zero.
  * Otherwise, the following values are added together:
    * If the condition is a `once` condition, add 1.
    * If the condition has an expression, add the the total number of boolean operators (and, or, not, xor) present, plus 1.
* A unique key that identifies the content.

{% hint style="info" %}
Here are some examples of calculating the complexity of `when:` headers:

* `when: always` has a complexity of 0.
* `when: $a` has a complexity of 1.
* `when: $a or $b` has a complexity of 2.
* `when: once` has a complexity of 1.
* `when: once if $a or $b` has a complexity of 3.
{% endhint %}

You can either use one of Yarn Spinner's built-in saliency strategies, or create your own custom saliency strategy.

### Yarn Spinner has several built-in saliency strategies.

* **First:** The first item in the group that has not failed any of its conditions is selected.
  * If the items of a node group are all in the same file, the ordering of the group is the order in which they appear in the file. If a node group’s nodes are split up across more than one file, the ordering of the nodes is not defined.
* **Best:** The items that have not failed any conditions are sorted by their total complexity score, and the first item that has the highest score is selected.
* **Best Least Recently Viewed:** The items that have not failed any conditions are sorted by score, and then by how many times they have been selected by this strategy. If there is more than one best item remaining, the first of these is selected.
* **Random Best Least Recently Viewed:** The items that have not failed any conditions are sorted by score, and then by how many times they have been selected by this strategy. If there is more than one best item remaining, a random one of these is selected.

If you don't set the saliency strategy anywhere yourself, the default will be **Random Best Least Recently Viewed.**

A saliency strategy is given a collection of possible options, and returns either one of them that should be run, or `null` to indicate that none of them should run.

{% hint style="danger" %}
You can only change the saliency strategy in Try Yarn Spinner and when using Yarn Spinner in a game engine, like Unity.&#x20;
{% endhint %}

### Changing the active saliency strategy in Try Yarn Spinner

When using Try Yarn Spinner, you can set the saliency strategy by calling one of the following built-in commands:

```
<<set_saliency first>>
<<set_saliency random>>
<<set_saliency best>>
<<set_saliency best_least_recent>>
<<set_saliency random_best_least_recent>>
```

### Changing the active saliency strategy in Yarn Spinner for Visual Studio Code

When using Visual Studio Code to Preview your dialouge, you can change the active saliency strategy in the drop-down menu at the top of the Preview view:

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 12.50.36 pm.png" alt=""><figcaption><p>Changing the saliency strategy in Visual Studio Code.</p></figcaption></figure>

### Creating Custom Saliency Strategies

Your C# code can create custom saliency strategies. To do so, create a type that implements the `IContentSaliencyStrategy` interface, and assign it to your `Dialogue` object’s `ContentSaliencyStrategy` property.

`IContentSaliencyStrategy` has two required methods.

* `ContentSaliencyOption? QueryBestContent(IEnumerable<ContentSaliencyOption> content)` determines which of a collection of options, if any, should run. It should return the best content from the available options, or `null` if none of them should run. This is the main method in which you write the specific logic for your custom strategy.
  * Calling this method does _not_ indicate that the content _has been selected;_ rather, it is a query to determine _what should be selected_. Your implementation of this method should not change any state, and should be read-only. The content returned by this method is not guaranteed to actually be run.
* `void ContentWasSelected(ContentSaliencyOption content)` is called to indicate that a specific piece of content returned by a previous call to `QueryBestContent` has been selected. This method should update any appropriate state to represent this fact, such as by updating the total number of times the content has been selected.

### Querying If Any Content Can Run

You can use a node group to check to see if any of its items can run, This can be useful when determining whether to show if a character should be marked as ready to talk, or whether any of its nodes have a special tag (for example, if a character has important information to discuss, as opposed to more general conversation.)
