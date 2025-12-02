---
description: Learn about storing data using variables in Yarn Spinner Scripts.
icon: binary
---

# Variables

Sometimes it makes sense for the options presented or the outcomes of selecting different options to vary based on other things the player has done or said up until this point. This requires the use of **logic** and **variables**, which we'll discuss in this section.

Yarn Spinner Script is a full programming language, which means it has support for writing code that let you control how the dialogue in your game works. In this section, you'll learn how to use **variables** to control your dialogue.

**Variables** store information. Variables can store one of three types of information: **numbers**, **strings**, and **booleans**.

Every variable has a name. In Yarn Spinner, all variable names start with a dollar sign (`$`).

## Declaring Variables

Declaring a variable means telling Yarn Spinner that a variable exists, what it's meant to be used for, and what initial value it has.

{% hint style="warning" %}
You should always declare a variable before you first use it.
{% endhint %}

To declare a variable, you use the `<<declare>>` command:

{% code lineNumbers="true" %}
```markup
/// The name of the player.
<<declare $playerName = "Reginald the Wizard">>

/// The number of gold pieces that the player has.
<<declare $gold = 42>>

/// Is the door to the dungeon unlocked?
<<declare $doorUnlocked = false>>
```
{% endcode %}

{% hint style="warning" %}
If you use a variable without declaring it, Yarn Spinner will try to figure out what type it should have based on how it's being used in your scripts, as well as what initial value it should have - zero for numbers, false for booleans, and blank text for strings. When a variable is not declared, we call that an _implicit_ declaration.

If you declare a variable, you can make sure that the type of the variable is what you intend it to be. Declaring a variable also lets you control what the variable's initial value is, and lets you add descriptive comments that explain the purpose of the variable to other people (or to your future self!)
{% endhint %}

You may find it useful to create a special node (for example, titled `Setup`, or similar) that is used solely to `<<declare>>` all the variables your narrative uses. You don't need to run this node for the declarations to take effect.

## Setting Variables

You put information into a variable by using the `<<set>>` command. For example, the following Yarn Spinner Script puts a string, `"Hello, Yarn!"`, into a variable called `$greeting`:

```
<<set $greeting to "Hello, Yarn!">>
```

{% hint style="warning" %}
As with node titles, variable names must not contain spaces. While they can contain a range of different characters the first character must be a letter. In general your variables will be made up of only letters, numbers and underscores.
{% endhint %}

## Variables and Types

Variables in Yarn Spinner can store one of three types of information: **numbers**, **strings**, and **booleans:**

<table><thead><tr><th width="136.33333333333331">Type</th><th>Possible Values</th><th>Examples</th></tr></thead><tbody><tr><td>Number</td><td>Any whole or decimal number</td><td><code>1</code>, <code>2.5</code>, <code>3468900</code>, <code>-500</code></td></tr><tr><td>String</td><td>Any sequence of letters, numbers and other characters, enclosed in quotes.</td><td>"<code>Hello</code>", "<code>✓</code>", "<code>A whole sentence.</code>"</td></tr><tr><td>Boolean</td><td>Either the value <em>true</em> or the value <em>false</em>.</td><td><code>true</code>, <code>false</code></td></tr></tbody></table>

Each variable can only store one type of value. Variables can change their value at any time, but they can never change their type.

For example, the following Yarn Spinner Script will work:

```markup
// Set some initial values in some variables
<<declare $myCoolNumber = 7>>
<<declare $myFantasticString = "wow, text!">>

// Now change them!
<<set $myCoolNumber to 8>>
<<set $myFantasticString to "incredible!">>
```

This works because while the value of each of the variable changes, the type doesn't change.

However, the following Yarn Spinner Script will **not** work:

```markdown
// Set some initial values in some variables
<<declare $myCoolNumber = 7>>
<<declare $myFantasticString = "wow, text!">>

// This will NOT work, because you can't change types!
<<set $myCoolNumber to "eight">>
<<set $myFantasticString to 42>>
```

This will not work because when they are declared, `$myCoolNumber` is set to a number, and `$myFantasticString` is set to a string, so they can only ever store that type of information.

{% hint style="danger" %}
Variables cannot be empty. All variables are **required** to have a value.
{% endhint %}

## Variables and Expressions

You can work with the values stored in variables.

For example, numbers can be multiplied, strings can be combined, and boolean values can have logical operations (like _and_ and _or_) applied to them. When values are used together like this, it's called an **expression:**

<pre><code><strong>// Stores 3 inside $numberOfSidesInATriangle
</strong><strong>&#x3C;&#x3C;set $numberOfSidesInATriangle = 2 + 1>>
</strong>
// Store 4 inside $numberOfSidesInASquare
&#x3C;&#x3C;set $numberOfSidesInASquare = $numberOfSidesInATriangle + 1>>
</code></pre>

An expression needs to be a single type. You can't work with values of different types in a single expression.

For example, the following code will **not** work:

```
// This will NOT work, because you can't add a string and a number:
<<set $broken = "hello" + 1>>
```

Yarn Spinner provides built-in functions for converting between certain types:

* The `string()` function converts values of any type into a string.
* The `number()` function converts values of any type into a number (if it can be interpreted as one.)
* The `bool()` function converts values of any type into a boolean value (if it can be interpreted as one.)

These functions work within Yarn Spinner Scripts. They all work by passing in, between the `(` and `)`, a value of any time, either directly or by referring to another variable, and they return the same value, converted to the appropriate type.

For example, consider the following:

```
<<declare $aNumber = 42>>
<<declare $aString = "This is my string.">>
<<set $aString = string($aNumber)>>
```

In this snippet, we declare the variable `$aNumber` and assign it the default value of `42`, so `$aNumber` will always store a number, and we declare the variable `$aString` and assign it the default value of `"This is a string"`, so `$aString` will always store a string.

Then, we use the `<<set>>` command to upate the value stored in `$aString`, and assign it the value of `$aNumber` (which is a number, and can't be assigned directly to a string) converted to a string using the `string()` function. Thus, `$aString` will then contain the string `"42"`.

## Operators

Yarn Spinner supports the following logical operators. Most of these have multiple ways being written:

* Equality: `eq` or `is` or `==`
* Inequality: `neq` or `!`
* Greater than: `gt` or `>`
* Less than: `lt` or `<`
* Less than or equal to: `lte` or `<=`
* Greater than or equal to: `gte` or `>=`
* Boolean 'or'': `or` or `||`
* Boolean 'xor': `xor` or `^`
* Boolean 'not': `not` or `!`
* Boolean 'and': `and` or `&&`

Yarn Spinner also supports the following maths operators:

* Addition: `+`
* Subtraction: `-`
* Multiplication: `*`
* Division: `/`
* Truncating Remainder Division: `%`
* Brackets: `(` to open the brackets and `)` to close them.

### Order of operations

Yarn Spinner follows a fairly standard order of operations, and falls back to using left to right when operators are of equivalent priority.

The order of operations is as follows:

1. Brackets
2. Boolean Negation
3. Multiplication, Division, and Truncating Remainder Division
4. Addition, Subtraction
5. Less than or equals, Greater than or equals, Less than, Greater than
6. Equality, Inequality
7. Boolean AND, Boolean OR, Boolean XOR

## Using Variables in Lines

To show the contents of a variable, you put it inside braces (`{ }`) inside a line. The value of that variable will appear in its place. For example:

{% tabs %}
{% tab title="Snippet" %}
```
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

## Write a story that uses variables

{% stepper %}
{% step %}
#### Create a Yarn Spinner Script that uses variables.

Create a new narrative that uses two variables that track a player name, and an amount of currency. Make sure you declare them.
{% endstep %}

{% step %}
#### Use the `<<set>>` command to update the value of the variables appropriately

Make sure you remember the types!
{% endstep %}
{% endstepper %}
