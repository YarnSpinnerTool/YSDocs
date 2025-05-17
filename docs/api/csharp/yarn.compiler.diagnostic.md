# Diagnostic

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


A diagnostic message that describes an error, warning or informational
message that the user can take action on.


```csharp
public sealed class Diagnostic
```

## Remarks


Diagnostics are presented to the user as the result of compilation,
through the  <a href="yarn.compiler.compilationresult.md">CompilationResult</a>  class's  <a href="yarn.compiler.compilationresult.diagnostics.md">Diagnostics</a>  property.


## Constructors

|Name|Description|
|:---|:---|
|[Diagnostic(string,IToken,string,DiagnosticSeverity)](/docs/api/csharp/yarn.compiler.diagnostic..ctor-4.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,ParserRuleContext?,string,DiagnosticSeverity)](/docs/api/csharp/yarn.compiler.diagnostic..ctor-3.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,string,DiagnosticSeverity)](/docs/api/csharp/yarn.compiler.diagnostic..ctor-1.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,DiagnosticSeverity)](/docs/api/csharp/yarn.compiler.diagnostic..ctor-2.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,Range,string,DiagnosticSeverity)](/docs/api/csharp/yarn.compiler.diagnostic..ctor-5.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|

## Enums

|Name|Description|
|:---|:---|
|[DiagnosticSeverity](/docs/api/csharp/yarn.compiler.diagnostic.diagnosticseverity.md)|The severity of the issue.|

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/yarn.compiler.diagnostic.equals.md)||
|[GetHashCode()](/docs/api/csharp/yarn.compiler.diagnostic.gethashcode.md)||
|[ToString()](/docs/api/csharp/yarn.compiler.diagnostic.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Column](/docs/api/csharp/yarn.compiler.diagnostic.column.md)|Gets the zero-indexed character number in FileName at which the issue begins.|
|[Context](/docs/api/csharp/yarn.compiler.diagnostic.context.md)|Gets or sets the source text of  <a href="yarn.compiler.diagnostic.filename.md">FileName</a>  containing the issue.|
|[FileName](/docs/api/csharp/yarn.compiler.diagnostic.filename.md)|Gets or sets the path, URI or file-name that the issue occurred in.|
|[Line](/docs/api/csharp/yarn.compiler.diagnostic.line.md)|Gets the zero-indexed line number in FileName at which the issue begins.|
|[Message](/docs/api/csharp/yarn.compiler.diagnostic.message.md)|Gets or sets the description of the issue.|
|[Range](/docs/api/csharp/yarn.compiler.diagnostic.range.md)|Gets or sets the range of the file indicated by  <a href="yarn.compiler.diagnostic.filename.md">FileName</a>  that the issue occurred in.|
|[Severity](/docs/api/csharp/yarn.compiler.diagnostic.severity.md)|Gets or sets the severity of the issue.|

