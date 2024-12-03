---
description: Learn about using smart variables that determine their value at run-time.
---

# Smart Variables

<figure><img src="../../.gitbook/assets/Smart Variables.png" alt=""><figcaption></figcaption></figure>

{% include "../../.gitbook/includes/this-version-of-the-documen....md" %}

In Yarn Spinner 3, smart variables let you create variables whose value is determined at run-time, rather than setting and retrieving a value from storage.&#x20;

{% hint style="info" %}
Smart variables give you a simple way to create more complex expressions, and re-use them across your project.
{% endhint %}

To create a smart variable, [declare it like any other variable](../../writing-dialogue-in-yarn/writing-in-yarn/logic-and-variables.md#declaring-variables) using the `declare` statement and provide an expression, rather than a single value:

```markdown
// A boolean value that is 'true' when the player has more than 10 money
<<declare $player_can_afford_pie = $player_money > 10>>
```

Smart variables can be accessed anywhere a regular variable would be used:

```markdown
// Run some lines if the player can afford a pie
<<if $player_can_afford_pie>>
  Player: One pie, please.
  PieMaker: Certainly!
<<endif>>
```
