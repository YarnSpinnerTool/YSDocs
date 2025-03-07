---
icon: binary
---

# Variables

Sometimes it makes sense for the options presented or the outcomes of selecting different options to vary based on other things the player has done or said up until this point. This requires the use of **logic** and **variables**, which we'll discuss in this section.

Yarn Spinner Script is a full programming language, which means it has support for writing code that let you control how the dialogue in your game works. In this section, you'll learn how to use **variables** to control your dialogue.

## Variables

**Variables** store information. Variables can store one of three types of information: **numbers**, **strings**, and **booleans**.

<table><thead><tr><th width="136.33333333333331">Type</th><th>Possible Values</th><th>Examples</th></tr></thead><tbody><tr><td>Number</td><td>Any whole or decimal number</td><td><code>1</code>, <code>2.5</code>, <code>3468900</code>, <code>-500</code></td></tr><tr><td>String</td><td>Any sequence of letters, numbers and other characters, enclosed in quotes.</td><td>"<code>Hello</code>", "<code>✓</code>", "<code>A whole sentence.</code>"</td></tr><tr><td>Boolean</td><td>Either the value <em>true</em> or the value <em>false</em>.</td><td><code>true</code>, <code>false</code></td></tr></tbody></table>

Every variable has a name. In Yarn Spinner, all variable names start with a dollar sign (`$`).

### Declaring Variables

_Declaring_ a variable means telling Yarn Spinner that a variable exists, what it's meant to be used for, and what initial value it has.

To declare a variable, you use the `<<declare>>` statement:

{% code lineNumbers="true" %}
```markup
/// The name of the player.
<<declare $playerName = "Player">>

/// The number of gold pieces that the player has.
<<declare $gold = 0>>

/// Is the door to the dungeon unlocked?
<<declare $doorUnlocked = false>>
```
{% endcode %}

{% hint style="warning" %}
If you use a variable without declaring it, Yarn Spinner will try to figure out what type it should have based on how it's being used in your scripts, as well as what initial value it should have - zero for numbers, false for booleans, and blank text for strings. When a variable is not declared, we call that an _implicit_ declaration.

If you declare a variable, you can make sure that the type of the variable is what you intend it to be. Declaring a variable also lets you control what the variable's initial value is, and lets you add descriptive comments that explain the purpose of the variable to other people (or to your future self!)&#x20;
{% endhint %}

You put information into a variable by using the `<<set>>` command. For example, the following code puts a _string_, `"Hello, Yarn!"`, into a variable called `$greeting`:

```
<<set $greeting to "Hello, Yarn!">>
```

{% hint style="warning" %}
As with node titles, variable names must not contain spaces. While they can contain a range of different characters the first character must be a letter. In general your variables will be made up of only letters, numbers and underscores.
{% endhint %}

### Variables and Types

Each variable can only store one type of value. Variables can change their value at any time, but they can never change their type.

For example, the following Yarn Spinner Script will work:

```
// Set some initial values in some variables
<<set $myCoolNumber to 7>>
<<set $myFantasticString to "wow, text!">>

// Now change them!
<<set $myCoolNumber to 8>>
<<set $myFantasticString to "incredible!">>
```

This works because while the value of each of the variable changes, the type doesn't. However, the following Yarn Spinner Script will **not** work:

```
// Set some initial values in some variables
<<set $myCoolNumber to 7>>
<<set $myFantasticString to "wow, text!">>

// This will NOT work, because you can't change types!
<<set $myCoolNumber to "8">>
<<set $myFantasticString to 42>>
```

{% hint style="info" %}
In earlier versions of Yarn Spinner, variables could also be `null`, which represented "no value". From with Yarn Spinner 2 onwards, variables are never `null`. All variables are required to have a value.
{% endhint %}

### Variables and Expressions

You can work with the values inside variables. For example, numbers can be multiplied, strings can be added together, and boolean values can have logical operations (like _and_ and _or_) applied to them. When values are used together like this, it's called an **expression**.

```
<<set $numberOfSidesInATriangle = 2 + 1>>

<<set $numberOfSidesInASquare = $numberOfSidesInATriangle + 1>>
```

An expression needs to be a single type. You can't work with values of different types in a single expression. For example, the following code will **not** work:

```
// This will NOT work, because you can't add a string and a number:
<<set $broken = "hello" + 1>>
```

{% hint style="info" %}
Yarn Spinner provides built-in functions for converting between certain types:

* The `string` function converts values of any type into a string.
* The `number` function converts values of any type into a number (if it can be interpreted as one.)
* The `bool` function converts values of any type into a boolean value (if it can be interpreted as one.)
{% endhint %}

#### Logical operators

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

#### Maths operators

* Addition: `+`
* Subtraction: `-`
* Multiplication: `*`
* Division: `/`
* Truncating Remainder Division: `%`
* Brackets: `(` to open the brackets and `)` to close them.

#### Order of operations

Yarn Spinner follows a fairly standard order of operations, and falls back to using left to right when operators are of equivalent priority.

The order of operations is as follows:

1. Brackets
2. Boolean Negation
3. Multiplication, Division, and Truncating Remainder Division
4. Addition, Subtraction
5. Less than or equals, Greater than or equals, Less than, Greater than
6. Equality, Inequality
7. Boolean AND, Boolean OR, Boolean XOR

### Using Variables in Lines

To show the contents of a variable, you put it inside braces (`{ }`) inside a line. The value of that variable will appear in its place.

For example:

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

{% stepper %}
{% step %}
### Create a Yarn Spinner Script in Try Yarn Spinner that uses variables.

Create a new narrative that uses two variables that track a player name, and an amount of currency.
{% endstep %}

{% step %}
###


{% endstep %}
{% endstepper %}



.
