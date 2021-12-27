# IndentAwareLexer

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `Antlr4.Runtime.Lexer`

## Summary


A Lexer subclass that detects newlines and generates indent and
dedent tokens accordingly.


```csharp
public abstract class IndentAwareLexer : Lexer
```

## Methods

|Name|Description|
|:---|:---|
|[IndentAwareLexer(ICharStream,TextWriter,TextWriter)](/api/csharp/yarn.compiler.indentawarelexer..ctor.md)|Initializes a new instance of the  <a href="yarn.compiler.indentawarelexer.md">IndentAwareLexer</a>  class.|
|[NextToken()](/api/csharp/yarn.compiler.indentawarelexer.nexttoken.md)||

## Properties

|Name|Description|
|:---|:---|
|[Warnings](/api/csharp/yarn.compiler.indentawarelexer.warnings.md)|Gets the collection of warnings determined during lexing.|

## Types

|Name|Description|
|:---|:---|
|[Warning](/api/csharp/yarn.compiler.indentawarelexer.warning.md)|A warning emitted during lexing.|

