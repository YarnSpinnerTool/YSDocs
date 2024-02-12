# SplitCommandText(string)

Method in [DialogueRunner](./)

## Summary

Splits input into a number of non-empty sub-strings, separated by whitespace, and grouping double-quoted strings into a single sub-string.

```csharp
public static IEnumerable<string> SplitCommandText(string input)
```

## Remarks

This method behaves similarly to the `System.String.Split(System.Char[],System.StringSplitOptions)` method with the `System.StringSplitOptions` parameter set to `System.StringSplitOptions.RemoveEmptyEntries` , with the following differences:

* Text that appears inside a pair of double-quote characters will not be split.
* Text that appears after a double-quote character and before the end of the input will not be split (that is, an unterminated double-quoted string will be treated as though it had been terminated at the end of the input.)
* When inside a pair of double-quote characters, the string `\\` will be converted to `\`, and the string `\"` will be converted to `"`.

## Parameters

| Name           | Description          |
| -------------- | -------------------- |
| `string` input | The string to split. |

## Returns

A collection of sub-strings.
