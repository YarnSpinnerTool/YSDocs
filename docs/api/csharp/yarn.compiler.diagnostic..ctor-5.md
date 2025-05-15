# Diagnostic(string,Range,string,DiagnosticSeverity)

Constructor in [Diagnostic](/docs/api/csharp/yarn.compiler.diagnostic.md)

## Summary


Initializes a new instance of the  [Diagnostic](yarn.compiler.diagnostic.md)  class.


```csharp
public Diagnostic(string fileName, Range range, string message, DiagnosticSeverity severity = DiagnosticSeverity.Error)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` fileName|Gets or sets the path, URI or file-name that the issue occurred in.|
|[Yarn.Compiler.Range](/docs/api/csharp/yarn.compiler.range.md) range|Gets or sets the range of the file indicated by  [FileName](yarn.compiler.diagnostic.filename.md)  that the issue occurred in.|
|`string` message|Gets or sets the description of the issue.|
|[Yarn.Compiler.Diagnostic.DiagnosticSeverity](/docs/api/csharp/yarn.compiler.diagnostic.diagnosticseverity.md) severity|Gets or sets the severity of the issue.|

