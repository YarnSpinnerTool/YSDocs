# ParseResult

Struct in [StructuredCommandParser](yarn.compiler.structuredcommandparser.md)

Inherits from `System.ValueType`

## Summary

Represents the result of a parse operation containing both the parsed context and diagnostics.

```csharp
public struct ParseResult
```

## Fields

| Name                                                                            | Description                                          |
| ------------------------------------------------------------------------------- | ---------------------------------------------------- |
| [context](yarn.compiler.structuredcommandparser.parseresult.context.md)         | The parsed structured command context.               |
| [diagnostics](yarn.compiler.structuredcommandparser.parseresult.diagnostics.md) | A collection of diagnostics produced during parsing. |

## Properties

| Name                                                                    | Description                                                                                       |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| [IsValid](yarn.compiler.structuredcommandparser.parseresult.isvalid.md) | Gets a value indicating whether the parse result is valid (that is, it contains no parse errors.) |
