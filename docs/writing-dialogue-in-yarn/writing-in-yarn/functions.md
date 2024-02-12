# Functions

A _function_ is a block of code that provides a value to your Yarn scripts, which you can use in [`if` statements](flow-control.md), or store in [variables](logic-and-variables.md).

In Yarn Spinner scripts, functions perform two main kinds of task:

* Functions let you get values that change over time, or that depend on other values. For example, the `random` function returns a different random number every time you call it.
* Functions let you get data from your game back into your scripts.

You call a function inside an expression. For example:

```yaml
// Inside an if statement:
<<if dice(6) == 6>>
    You rolled a six!
<<endif>>

// Inside a line:
Gambler: My lucky number is {random_range(1,10)}!
```

## Built-In Functions

Yarn Spinner comes with several built-in functions for you to use.

### `visited(string node_name)`

`visited` returns a boolean value of `true` if the node with the title of `node_name` has been entered and exited at least once before, otherwise returns `false`. Will return `false` if `node_name` doesn't match a node in project.

### `visited_count(string node_name)`

`visted_count` returns a number value of the number of times the node with the title of `node_name` has been entered and exited, otherwise returns `0`. Will return `0` if `node_name` doesn't match a node in project.

### `format_invariant(number n)`

`format_invariant` returns a string representation of `n`, formatted using the invariant culture. This is useful for embedding numbers in commands, where the command expects the number to be formatted using the invariant culture. For example, `<<give_gold {$gold}>>`, which might end up as `give_gold 4,51` in German, but `give_gold 4.51` in English, can now be `<<give_gold {format_invariant($gold)}>>`, which will always be `give_gold 4.51`.

### `random()`

`random` returns a random number between 0 and 1 each time you call it.

### `random_range(number a, number b)`

`random_range` returns a random number between `a` and `b`, inclusive.

### `dice(number sides)`

`dice` returns a random integer between 1 and `sides`, inclusive.

For example, `dice(6)` returns a number between 1 and 6, just like rolling a six-sided die.

### `round(number n)`

`round` rounds `n` to the nearest integer.

### `round_places(number n, number places)`

`round_places` rounds `n` to the nearest number with `places` decimal points.

### `floor(number n)`

`floor` rounds `n` down to the nearest integer, towards negative infinity.

### `ceil(number n)`

`ceil` rounds `n` up to the nearest integer, towards positive infinity.

### `inc(number n)`

`inc` rounds `n` up to the nearest integer. If `n` is already an integer, `inc` returns `n+1`.

### `dec(number n)`

`dec` rounds `n` down to the nearest integer. If `n` is already an integer, `dec` returns `n-1`.

### `decimal(number n)`

`decimal` returns the decimal portion of `n`. This will always be a number between 0 and 1. For example, `decimal(4.51)` will return `0.51`.

### `int(number n)`

`int` rounds `n` down to the nearest integer, towards zero.

{% hint style="info" %}
This is different to `floor`, because `floor` rounds to negative infinity.
{% endhint %}

## Custom Functions

You can define your own custom functions in Yarn Spinner. For more information, see [# Defining Commands and Functions ](../../yarn-spinner-for-unity/creating-commands-functions.md).

{% hint style="warning" %}
Functions are not intended to be a way for you to send instructions to your game. For that purpose, you should use [commands](commands.md).

In particular, functions are not guaranteed to be called in the same order as they appear in your code, or even be called at all if Yarn Spinner believes the result can be cached. As much as possible, custom functions should be [pure functions](https://en.wikipedia.org/wiki/Pure\_function), and have no side effects besides returning a value based on parameters.
{% endhint %}
