---
description: Learn how to use logic and flow control in your Yarn Spinner Scripts.
icon: arrow-progress
---

# Flow Control

So far, you've learned how to use [lines-nodes-and-options.md](../lines-nodes-and-options.md "mention"), [options.md](../options.md "mention"), the [jumps.md](../jumps.md "mention"), the [detour.md](detour.md "mention"), and [logic-and-variables.md](logic-and-variables.md "mention") to write Yarn Spinner Scripts. Because it's actually a full programming language of its own, Yarn Spinner also supports **flow control**.&#x20;

Flow control takes several forms, including **if statements**, and **conditional options**.

## `if` statements

In addition to storing information, variables are useful for controlling what's lines of dialogue are presented to the player. To do this, you can use `if` statements.

An `if` statement allows you to control whether a collection of content is shown or not. When you write an `if` statement, you provide an _expression_, which is checked; if that expression evaluates to a `true` value, then all of the content in between the `<<if>>` and `<<endif>>` statements are run.

For example, consider the following Yarn Spinner Script:

```markup
<<set $gold_amount to 5>>

Player: I'd like to buy a pie!

<<if $gold_amount < 10>>
    Baker: Well, you can't afford one!
<<endif>>

```

This script will:

* set a variable, `$gold_amount`, to 5;
* show the line `Player: I'd like to buy a pie!`&#x20;
* use an if statement to see if `$gold_amount` is less than `10`, and if that is the case, which it will be in this example, show the line `Baker: Well, you can't afford one!`&#x20;

## `elseif` and `else`

You can use the `elseif` and `else` statements to handle different situations in an `if` statement.

An `elseif` statement has an expression that gets checked if the `if` statement, or any previous `elseif` statements, don't run.

An `else` statement doesn't have an expression, and runs if the `if` and any `elseif` don't run.

For example, consider the following Yarn Spinner Script:

```markup
<<set $gold_amount to 5>>
Player: I'd like to buy a pie!

<<if $gold_amount < 10>>
    Baker: Well, you can't afford one!
<<elseif $gold_amount < 15>>
    Baker: You can almost afford one!
<<else>>
    Baker: You can afford a pie!
<<endif>>
```

This script will:

* set a variable, `$gold_amount`, to 5;
* show the line `Player: I'd like to buy a pie!`&#x20;
* use an if statement to see if `$gold_amount` is less than `10`, and if that is the case, show the line `Baker: Well, you can't afford one!`&#x20;
  * otherwise use a `elseif` statement to see if `$gold_amount` is less than `15`, and if that is the case, show the line `Baker: You can almost afford one!`&#x20;
  * otherwise use a `else` statement to provide a fallback, which will show the line `Baker: You can afford a pie!`&#x20;
* end the `if` statement block with an `endif` statement.

You can have as many `elseif` statements as you want inside an `if` statement block, and you can use whatever [#operators](logic-and-variables.md#operators "mention") you want inside, for example:

```markup
<<set $gold_amount to 5>>
<<set $reputation to 10>>
<<if $gold_amount >= 5 and $reputation >= 8>>
    // The player is both rich and popular
    Merchant: You're rich enough and popular enough for me to serve you!
<<elseif $gold_amount >= 10 or $reputation >= 10>>
    // The player is either rich enough or popular enough to serve
    Merchant: I wouldn't normally, but I'll serve you!
<<else>>
    // The player is dirt
    Merchant: You're neither rich enough nor important enough for me to serve!
<<endif>>
```

In this example:

* there are two variables, `$gold_amount` for tracking the player's currency, and `$reputation` for their reputation in town
* an `if` statement first checks if their `$gold_amount` is greater than or equal to `5` **and** whether their reputation is greater than or equal to `8`, if **both of these are true**,  then the line `Merchant: You're rich enough and popular enough for me to serve you!`  is shown
  * otherwise the elseif statement checks if their $gold\_amount is greater than or equal to 10 (making them very rich), **or** their $reputation is greater than or equal to 10 (making them very well regarded), and if **either of these are true the line** `Merchant: I wouldn't normally, but I'll serve you!`  is shown
* if neither set of conditions is true, then the else statement means the line `Merchant: You're neither rich enough nor important enough for me to serve!`  will be shown

{% hint style="info" %}
`The` expression used in an `if` and `elseif` statement must result in a boolean value (that is, true or false.) For exame,`<<if 1>>` isn't allowed, but `<<if 1 == 1>>` is.
{% endhint %}

## Conditional Options

When presenting options to the player using the `->` syntax, you may want to make some options not available. You can do this by adding a condition to the option, making it a **conditional option**.

For example, if you have a variable that tracks your player's reputation points, called `$reputation`, you might want to make certain options only available if the value of `$reputation` is high enough.

Conditions on options are done by adding an `if` statement to the end of the option. They look like this:

```css
Guard: You're not allowed in!
-> Sure I am! The boss knows me! <<if $reputation > 10>>
-> Please?
-> I'll come back later.
```

When Yarn Spinner runs this collection of options, it will check the expression inside the `if` statement. If the expression is `false`, then the option will be marked as _unavailable_.

{% hint style="info" %}
Yarn Spinner always delivers _every_ option in an option group to the game; it's up to the game to decide what to do with options that are marked as unavailable.

For example, an unavailable option might be shown to the user, but not selectable, so that the user can see that they _could_ have been able to say that if circumstances had been different.
{% endhint %}

Now that you know how to work with [nodes](../lines-nodes-and-options.md#nodes), [lines](../lines-nodes-and-options.md#lines), [options](../lines-nodes-and-options.md#options) and [variables](logic-and-variables.md#variables), there's one last part of the Yarn language to learn about: **commands**.
