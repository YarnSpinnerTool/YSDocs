# IndentAwareLexer

Class in [Yarn.Compiler](yarn.compiler.md)

Inherits from `Antlr4.Runtime.Lexer`

## Summary

A Lexer subclass that detects newlines and generates indent and\
dedent tokens accordingly.

```csharp
public abstract class IndentAwareLexer : Lexer
```

## Constructors

| Name                                                                                           | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [IndentAwareLexer(ICharStream,TextWriter,TextWriter)](yarn.compiler.indentawarelexer..ctor.md) | Initializes a new instance of the [IndentAwareLexer](yarn.compiler.indentawarelexer.md) class. |

## Methods

| Name                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| [IsInWhenClause()](yarn.compiler.indentawarelexer.isinwhenclause.md)       | Returns a value indicating whether the lexer is currently lexing an expression that's part of a 'when' clause. |
| [NextToken()](yarn.compiler.indentawarelexer.nexttoken.md)                 |                                                                                                                |
| [SetInWhenClause(bool)](yarn.compiler.indentawarelexer.setinwhenclause.md) | Sets a value indicating whether the lexer is currently lexing an expression that's part of a 'when' clause.    |

## Properties

| Name                                                   | Description                                               |
| ------------------------------------------------------ | --------------------------------------------------------- |
| [Warnings](yarn.compiler.indentawarelexer.warnings.md) | Gets the collection of warnings determined during lexing. |

## Structs

| Name                                                           | Description                      |
| -------------------------------------------------------------- | -------------------------------- |
| [LexerWarning](yarn.compiler.indentawarelexer.lexerwarning.md) | A warning emitted during lexing. |
