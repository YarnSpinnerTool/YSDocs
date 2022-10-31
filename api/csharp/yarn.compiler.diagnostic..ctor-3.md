# Diagnostic(string,ParserRuleContext,string,DiagnosticSeverity)

Constructor in [Diagnostic](api/csharp/yarn.compiler.diagnostic.md)

## Summary


Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.


```csharp
public Diagnostic(string fileName, ParserRuleContext context, string message, DiagnosticSeverity severity = DiagnosticSeverity.Error)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` fileName|Gets or sets the path, URI or file-name that the issue occurred in.|
|`Antlr4.Runtime.ParserRuleContext` context|The parse node at which the error occurred.|
|`string` message|Gets or sets the description of the issue.|
|[Yarn.Compiler.Diagnostic.DiagnosticSeverity](api/csharp/yarn.compiler.diagnostic.diagnosticseverity.md) severity|Gets or sets the severity of the issue.|

