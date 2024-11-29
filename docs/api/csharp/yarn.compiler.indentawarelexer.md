# IndentAwareLexer

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `Antlr4.Runtime.Lexer`

## Summary


A Lexer subclass that detects newlines and generates indent and
dedent tokens accordingly.


```csharp
public abstract class IndentAwareLexer : Lexer
```

## Constructors

|Name|Description|
|:---|:---|
|[IndentAwareLexer(ICharStream,TextWriter,TextWriter)](/docs/api/csharp/yarn.compiler.indentawarelexer..ctor.md)|Initializes a new instance of the  <a href="yarn.compiler.indentawarelexer.md">IndentAwareLexer</a>  class.|

## Methods

|Name|Description|
|:---|:---|
|[IsInWhenClause()](/docs/api/csharp/yarn.compiler.indentawarelexer.isinwhenclause.md)|Returns a value indicating whether the lexer is currently lexing an expression that's part of a 'when' clause.|
|[NextToken()](/docs/api/csharp/yarn.compiler.indentawarelexer.nexttoken.md)||
|[SetInWhenClause(bool)](/docs/api/csharp/yarn.compiler.indentawarelexer.setinwhenclause.md)|Sets a value indicating whether the lexer is currently lexing an expression that's part of a 'when' clause.|

## Properties

|Name|Description|
|:---|:---|
|[Warnings](/docs/api/csharp/yarn.compiler.indentawarelexer.warnings.md)|Gets the collection of warnings determined during lexing.|

## Structs

|Name|Description|
|:---|:---|
|[LexerWarning](/docs/api/csharp/yarn.compiler.indentawarelexer.lexerwarning.md)|A warning emitted during lexing.|

