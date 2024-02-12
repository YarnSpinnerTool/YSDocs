# FileParseResult

Struct in [Yarn.Compiler](../)

Inherits from `System.ValueType`

## Summary

Contains the result of parsing a single file of source code.

```csharp
public struct FileParseResult
```

## Remarks

This class provides only syntactic information about a parse - that is, it provides access to the parse tree, and the stream of tokens used to produce that parse tree.

## Constructors

| Name                                                                                           | Description                                                     |
| ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [FileParseResult(string,IParseTree,CommonTokenStream)](yarn.compiler.fileparseresult..ctor.md) | Initializes a new instance of the [FileParseResult](./) struct. |

## Methods

| Name                                                          | Description |
| ------------------------------------------------------------- | ----------- |
| [Equals(object)](yarn.compiler.fileparseresult.equals.md)     |             |
| [GetHashCode()](yarn.compiler.fileparseresult.gethashcode.md) |             |

## Properties

| Name                                              | Description                             |
| ------------------------------------------------- | --------------------------------------- |
| [Name](yarn.compiler.fileparseresult.name.md)     | The name of the file.                   |
| [Tokens](yarn.compiler.fileparseresult.tokens.md) | The tokens extracted from the file.     |
| [Tree](yarn.compiler.fileparseresult.tree.md)     | The parse tree extracted from the file. |
