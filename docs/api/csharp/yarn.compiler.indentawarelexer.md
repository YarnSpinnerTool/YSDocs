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
|[NextToken()](/docs/api/csharp/yarn.compiler.indentawarelexer.nexttoken.md)||

## Properties

|Name|Description|
|:---|:---|
|[Warnings](/docs/api/csharp/yarn.compiler.indentawarelexer.warnings.md)|Gets the collection of warnings determined during lexing.|

## Structs

|Name|Description|
|:---|:---|
|[Warning](/docs/api/csharp/yarn.compiler.indentawarelexer.warning.md)|A warning emitted during lexing.|

