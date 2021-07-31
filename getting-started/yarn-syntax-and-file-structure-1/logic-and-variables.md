# Variables and Logic

The Yarn language is a full programming language, which means it has support for writing code that let you control how the dialogue in your game works. In this section, you'll learn how to use **variables** to control your dialogue.

{% hint style="info" %}
This page discusses using variables inside Yarn scripts. To learn how to work with variables outside of Yarn Spinner, see **TODO**.
{% endhint %}

## Variables

**Variables** store information. Variables can store one of three types of information: **numbers**, **strings**, and **booleans**.

| Type | Possible Values | Examples |
| :--- | :--- | :--- |
| Number | Any whole or decimal number | 1, 2.5, 3468900, -500 |
| String | Any sequence of letters, numbers and other characters, enclosed in quotes. | "Hello", "✓", "A whole sentence." |
| Boolean | Either the value _true_ or the value _false_. | true, false |

Every variable has a name. In Yarn Spinner, all variable names start with a dollar sign \(`$`\).

### Setting Variables

You put information into a variable by using the `<<set>>` command. For example, the following code puts a _string_, `"Hello, Yarn!"`, into a variable called `$greeting`:

```text
<<set $greeting to "Hello, Yarn!">>
```

{% hint style="warning" %}
As with node titles, variable names must not contain spaces. They must be made up of only letters, numbers and underscores, and the first character must be a letter.
{% endhint %}

### Variables and Types

Each variable can only store one type of value. Variables can change their value at any time, but they can never change their type.

For example, the following code will work:

```text
// Set some initial values in some variables
<<set $myCoolNumber to 7>>
<<set $myFantasticString to "wow, text!">>

// Now change them!
<<set $myCoolNumber to 8>>
<<set $myFantasticString to "incredible!">>
```

This works because while the value of each of the variable changes, the type doesn't. However, the following code will **not** work:

```text
// Set some initial values in some variables
<<set $myCoolNumber to 7>>
<<set $myFantasticString to "wow, text!">>

// This will NOT work, because you can't change types!
<<set $myCoolNumber to "8">>
<<set $myFantasticString to 42>>
```

{% hint style="info" %}
Starting with Yarn Spinner 2.0, variables are never `null`. All variables are required to have a value.
{% endhint %}

```text
<<set $variableName to "a string value">>
```

### Variables and Expressions

You can work with the values inside variables. For example, numbers can be multiplied, strings can be added together, and boolean values can have logical operations \(like _and_ and _or_\) applied to them. When values are used together like this, it's called an **expression**.

```text
<<set $numberOfSidesInATriangle = 2 + 1>>

<<set $numberOfSidesInASquare = $numberOfSidesInATriangle + 1>>
```

An expression needs to be a single type. You can't work with values of different types in a single expression. For example, the following code will **not** work:

```text
// This will NOT work, because you can't add a string and a number:
<<set $broken = "hello" + 1>>
```

{% hint style="info" %}
Yarn Spinner provides functions for converting between certain types. For more information, see **TODO**.
{% endhint %}

### Using Variables in Lines

To show the contents of a variable, you put it inside braces \(`{ }`\) inside a line. The value of that variable will appear in its place.

For example:

{% tabs %}
{% tab title="Snippet" %}
```text
<<set $variableName to "a string value">>
The value of variableName is {$variableName}.
```
{% endtab %}

{% tab title="Output" %}
```
The value of variableName is a string value.
```
{% endtab %}
{% endtabs %}

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

Now that you know how to work with [nodes](lines-nodes-and-options.md#nodes), [lines](lines-nodes-and-options.md#lines), [options](lines-nodes-and-options.md#options) and [variables](logic-and-variables.md#variables), there's one last part of the Yarn language to learn about: **commands**.

