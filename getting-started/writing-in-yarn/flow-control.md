# Flow Control

## `if` statements

In addition to storing information, variables are useful for controlling what's shown to the player. To do this, you use `if` statements.

An `if` statement allows you to control whether a collection of content is shown or not. When you write an `if` statement, you provide an _expression_, which is checked; if that expression evaluates to a "true" value, then all of the content in between the `<<if>>` and `<<endif>>` statements are run.

For example, consider the following code:

```text
<<set $gold_amount to 5>>

Player: I'd like to buy a pie!

<<if $gold_amount < 10>>
    Baker: Well, you can't afford one!
<<endif>>

```

This example will set a variable, `$gold_amount`, to 5. It will then show the line "I'd like to buy a pie!", and before it continues, it will check to see if `$gold_amount` is less than 10. If that's the case \(which it will be!\), the line "Well, you can't afford one!" will run.

### `elseif` and `else`

You can use the `elseif` and `else` statements to handle different situations in an `if` statement. 

An `elseif` statement has an expression that gets checked if the `if` statement, or any previous `elseif` statements, don't run. 

An `else` statement doesn't have an expression, and runs 

For example:

```text
Player: I'd like to buy a pie!

<<if $gold_amount < 10>>
    Baker: Well, you can't afford one!
<<elseif $gold_amount < 15>>
    Baker: You can almost afford one!
<<else>>
    Baker: Here you go!
<<endif>>
```

This script will show different lines depending on the value of `$gold_amount`. The checks are done from top to bottom, which means that in order for an `elseif` or `else` to run, all of the checks above it have to have failed.

* If it's less than 10, the line "Well, you can't afford one!" will run.
* Otherwise, if it's less than 15, the line "You can almost afford one!" will run.
* Otherwise, the line "Here you go!" will run.

{% hint style="info" %}
The expression used in an `if` and `elseif` statement must result in a boolean value \(that is, true or false.\) For exame,`<<if 1>>` isn't allowed, but `<<if 1 == 1>>` is.
{% endhint %}

## Conditional Options

When presenting options to the player, you may want to make some options not available. You can do this by adding a _condition_ to the option.

For example, if you have a variable that tracks your player's "reputation points", called `$reputation`, you might want to make certain options only available if the value of `$reputation` is high enough.

Conditions on options are done by adding an `if` statement to the end of the option. They look like this:

```text
Guard: You're not allowed in!

-> Sure I am! The boss knows me! <<if $reputation > 10>>
-> Please?
```

When Yarn Spinner runs this collection of options, it will check the expression inside the `if` statement. If the expression is `false`, then the option will be marked as _unavailable._

{% hint style="info" %}
Yarn Spinner always delivers _every_ option in an option group to the game; it's up to the game to decide what to do with options that are marked as unavailable.

For example, an unavailable option might be shown to the user, but not selectable, so that the user can see that they _could_ have been able to say that if circumstances had been different.
{% endhint %}

Now that you know how to work with [nodes](lines-nodes-and-options.md#nodes), [lines](lines-nodes-and-options.md#lines), [options](lines-nodes-and-options.md#options) and [variables](logic-and-variables.md#variables), there's one last part of the Yarn language to learn about: **commands**.

