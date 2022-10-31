# DialogueRunner.SplitCommandText(string)

Method in [DialogueRunner](api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Splits input into a number of non-empty sub-strings, separated
by whitespace, and grouping double-quoted strings into a single
sub-string.


```csharp
public static IEnumerable<string> SplitCommandText(string input)
```

## Remarks


This method behaves similarly to the  <code>string.Split(char[], StringSplitOptions)</code>  method with
the  <code>StringSplitOptions</code>  parameter set to  <code>StringSplitOptions.RemoveEmptyEntries</code> , with the
following differences:

<ul type="bullet">
<li>Text that appears inside a pair of double-quote
characters will not be split.</li>
<li>Text that appears after a double-quote character and
before the end of the input will not be split (that is, an
unterminated double-quoted string will be treated as though it
had been terminated at the end of the input.)</li>
<li>When inside a pair of double-quote characters, the string
<code>\\</code> will be converted to <code>\</code>, and the string
<code>\"</code> will be converted to <code>"</code>.</li>
</ul>

## Parameters

|Name|Description|
|:---|:---|
|`string` input|The string to split.|

## Returns

A collection of sub-strings.

