# Logic and variables

**Variables** store single values that can be changed or checked later with a simple name. A variable must be given a value before it can be checked, and though it may change value it can never change from its initial **type**. There are three types to choose from:

| Type | Possible Values | Examples |
| :--- | :--- | :--- |
| Number | Any whole or decimal number | 1, 2.5, 3468900, -500 |
| String | Any sequence of characters \(enclosed in quotes\) | "Hello", "✓", "A whole sentence." |
| Boolean | Either the value true or the value false | true, false |

Variables of any type can also be set to `null` to indicate it has no value at the moment. Setting the initial value or changing the value of a variable is done with the `set` command. Variable names are indicated with a `$` at the start.

```text
<<set $variableName to "a string value">>
```

{% hint style="warning" %}
As with node titles, variable names must not contain spaces. They must be made up of only letters, numbers and underscores, and the first character must be a letter.
{% endhint %}

The easiest way to check the value of a variable is to include it in a line. To make the value of the variable be shown instead of its name, it must be enclosed in `{ }` brackets.

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



