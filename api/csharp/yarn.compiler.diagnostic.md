# Diagnostic

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

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
|[Diagnostic(string,ParserRuleContext,string,DiagnosticSeverity)](/api/csharp/yarn.compiler.diagnostic..ctor-3.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,string,DiagnosticSeverity)](/api/csharp/yarn.compiler.diagnostic..ctor-1.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,DiagnosticSeverity)](/api/csharp/yarn.compiler.diagnostic..ctor-2.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|
|[Diagnostic(string,Range,string,DiagnosticSeverity)](/api/csharp/yarn.compiler.diagnostic..ctor-4.md)|Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.|

## Enums

|Name|Description|
|:---|:---|
|[DiagnosticSeverity](/api/csharp/yarn.compiler.diagnostic.diagnosticseverity.md)|The severity of the issue.|

## Fields

|Name|Description|
|:---|:---|
|[Context](/api/csharp/yarn.compiler.diagnostic.context.md)|The source text of  <a href="yarn.compiler.diagnostic.filename.md">FileName</a>  containing the issue.|
|[FileName](/api/csharp/yarn.compiler.diagnostic.filename.md)|The path, URI or file-name that the issue occurred in.|
|[Message](/api/csharp/yarn.compiler.diagnostic.message.md)|The description of the issue.|
|[Range](/api/csharp/yarn.compiler.diagnostic.range.md)|The range of the file indicated by  <a href="yarn.compiler.diagnostic.filename.md">FileName</a>  that the issue occurred in.|
|[Severity](/api/csharp/yarn.compiler.diagnostic.severity.md)|The severity of the issue.|

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/api/csharp/yarn.compiler.diagnostic.equals.md)||
|[GetHashCode()](/api/csharp/yarn.compiler.diagnostic.gethashcode.md)||
|[ToString()](/api/csharp/yarn.compiler.diagnostic.tostring.md)||

## Properties

|Name|Description|
|:---|:---|
|[Column](/api/csharp/yarn.compiler.diagnostic.column.md)|Gets the zero-indexed character number in FileName at which the issue begins.|
|[Line](/api/csharp/yarn.compiler.diagnostic.line.md)|Gets the zero-indexed line number in FileName at which the issue begins.|

