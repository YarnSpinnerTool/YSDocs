---
description: >-
  Learn about saliency and saliency strategies, which let you control how line
  groups and node groups select which content to run.
---

# Saliency

In Yarn Spinner 3, saliency lets you control how [line groups](../../editing-with-vs-code/line-groups.md) and [node groups](./) select which content to run.

When a line group or node group needs to run content, it needs to make a decision about which item in the group to choose. The method for making this decision is called a _saliency strategy_.

Saliency strategies are provided with the following information about each item:

* How many of its conditions passed (that is, the `when:` clauses on a node group, or the single condition on a line group)
* How many of its conditions failed
* The total complexity of all of its conditions
  * Complexity is calculated as the total number of boolean operators (and, or, not, xor) present in a condition, plus 1 if the condition is a `once` condition. The `always` condition has a complexity of zero.
* A unique key that identifies the content.

You can either use one of Yarn Spinner's built-in saliency stragegies, or create your own custom saliency strategy.

### Yarn Spinner has several built-in saliency strategies.

* **First:** The first item in the group that has not failed any of its conditions is selected.
  * If the items of a node group are all in the same file, the ordering of the group is the order in which they appear in the file. If a node group’s nodes are split up across more than one file, the ordering of the nodes is not defined. the node that is considered ‘first’ is not defined.
* **Best:** The items that have not failed any conditions are sorted by their total complexity score, and the first item that has the highest score is selected.
* **Best Least Recently Viewed:** The items that have not failed any conditions are sorted by score, and then by how many times they have been selected by this strategy. If there is more than one best item remaining, the first of these is selected.
* **Random Best Least Recently Viewed:** The items that have not failed any conditions are sorted by score, and then by how many times they have been selected by this strategy. If there is more than one best item remaining, a random one of these is selected.

A saliency strategy is given a collection of possible options, and returns either one of them that should be run, or `null` to indicate that none of them should run.

### Creating Custom Saliency Strategies

Your C# code can create custom saliency strategies. To do so, create a type that implements the `IContentSaliencyStrategy` interface, and assign it to your `Dialogue` object’s `ContentSaliencyStrategy` property.

`IContentSaliencyStrategy` has two required methods.

* `ContentSaliencyOption? QueryBestContent(IEnumerable<ContentSaliencyOption> content)` determines which of a collection of options, if any, should run. It should return the best content from the available options, or `null` if none of them should run. This is the main method in which you write the specific logic for your custom strategy.
  * Calling this method does _not_ indicate that the content _has been selected;_ rather, it is a query to determine _what should be selected_. Your implementation of this method should not change any state, and should be read-only. The content returned by this method is not guaranteed to actually be run.
* `void ContentWasSelected(ContentSaliencyOption content)` is called to indicate that a specific piece of content returned by a previous call to `QueryBestContent` has been selected. This method should update any appropriate state to represent this fact, such as by updating the total number of times the content has been selected.

### Querying If Any Content Can Run

You can use a node group to check to see if any of its items can run, This can be useful when determining whether to show if a character should be marked as ready to talk, or whether any of its nodes have a special tag (for example, if a character has important information to discuss, as opposed to more general conversation.)
