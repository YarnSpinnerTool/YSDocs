# ParseSource(string)

Method in [Utility](./)

## Summary

Parses a string of Yarn source code, and produces a FileParseResult and (if there were any problems) a collection of diagnostics.

```csharp
public static (FileParseResult, IEnumerable<Diagnostic>) ParseSource(string source)
```

## Parameters

| Name            | Description               |
| --------------- | ------------------------- |
| `string` source | The source code to parse. |

## Returns

A tuple containing a [FileParseResult](../yarn.compiler.fileparseresult/) that stores the parse tree and tokens, and a collection of [Diagnostic](../yarn.compiler.diagnostic/) objects that describe problems in the source code.
