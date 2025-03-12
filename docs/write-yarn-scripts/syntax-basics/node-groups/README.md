---
description: >-
  Learn about using node groups, which allow Yarn Spinner to choose which
  content to run, depending on conditions.
icon: memo
---

# Node Groups

In Yarn Spinner 3, you can now create node groups. A node group is collection of nodes **that share the same name** that Yarn Spinner will choose from.&#x20;

To create a node group, you create multiple nodes that all share the same name, and ensure that each of the nodes have at least one `when:` header.&#x20;

The `when:`header tells Yarn Spinner about the conditions that must be met in order to run the node:

<pre class="language-html"><code class="lang-html">title: Guard
<a data-footnote-ref href="#user-content-fn-1">when: once</a>
---
Guard: You there, traveller!
Player: Who, me?
Guard: Yes! Stay off the roads after dark!
===
title: Guard
<a data-footnote-ref href="#user-content-fn-2">when: always</a>
---
Guard: I hear the king has a new advisor.
===
title: Guard
<a data-footnote-ref href="#user-content-fn-3">when: $has_sword</a>
---
Guard: No weapons allowed in the city!
===

</code></pre>

Node groups are combined into a single node that performs the appropriate checks and then runs one of the node group’s members. You start dialogue with a node group using its name. You can also use the `jump` or `detour` statements to run a node group from somewhere else in your Yarn scripts.

{% hint style="info" %}
Node groups are similar to [line groups](../../editing-with-vs-code/line-groups.md) in their behaviour, but give you more room to create longer passages of content. Your C# code can also check to see how many (if any) nodes can run, which is covered in the Saliency section.
{% endhint %}

You can have&#x20;

[^1]: this version of the node can only run once

[^2]: this version is the line can run any time

[^3]: this version of the node can only run if the variable `$has_sword` is true
