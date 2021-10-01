# Variables

The Yarn language is a full programming language, which means it has support for writing code that let you control how the dialogue in your game works. In this section, you'll learn how to use **variables** to control your dialogue.

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

## Variables and Storage

Yarn Spinner doesn’t manage the storage of information in variables itself. Instead, your game provides a _variable storage_ object to Yarn Spinner before you start running dialogue.

When Yarn Spinner needs to know the value of a variable, it will ask the variable storage object you’ve given it. When Yarn Spinner wants to set the value of a variable, it will provide the value and the name of the variable. In this way, your game has control over how data is stored.

To learn more about variable storage, see **TODO**.

