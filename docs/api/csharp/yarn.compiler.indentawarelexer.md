# IndentAwareLexer

Class in [Yarn.Compiler](yarn.compiler.md)

Inherits from `Antlr4.Runtime.Lexer`

## Summary

A Lexer subclass that detects newlines and generates indent and dedent tokens accordingly.

```csharp
public abstract class IndentAwareLexer : Lexer
```

## Constructors

| Name                                                                                           | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [IndentAwareLexer(ICharStream,TextWriter,TextWriter)](yarn.compiler.indentawarelexer..ctor.md) | Initializes a new instance of the [IndentAwareLexer](yarn.compiler.indentawarelexer.md) class. |

## Methods

| Name                                                       | Description |
| ---------------------------------------------------------- | ----------- |
| [NextToken()](yarn.compiler.indentawarelexer.nexttoken.md) |             |

## Properties

| Name                                                   | Description                                               |
| ------------------------------------------------------ | --------------------------------------------------------- |
| [Warnings](yarn.compiler.indentawarelexer.warnings.md) | Gets the collection of warnings determined during lexing. |

## Structs

| Name                                                 | Description                      |
| ---------------------------------------------------- | -------------------------------- |
| [Warning](yarn.compiler.indentawarelexer.warning.md) | A warning emitted during lexing. |
