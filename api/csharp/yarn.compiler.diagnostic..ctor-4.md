# Diagnostic(string,Range,string,DiagnosticSeverity)

Constructor in [Diagnostic](/api/csharp/yarn.compiler.diagnostic.md)

## Summary


Initializes a new instance of the  <a href="yarn.compiler.diagnostic.md">Diagnostic</a>  class.


```csharp
public Diagnostic(string fileName, Range range, string message, DiagnosticSeverity severity = DiagnosticSeverity.Error)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` fileName|The path, URI or file-name that the issue occurred in.|
|[Yarn.Compiler.Range](/api/csharp/yarn.compiler.range.md) range|The range of the file indicated by  <a href="yarn.compiler.diagnostic.filename.md">FileName</a>  that the issue occurred in.|
|`string` message|The description of the issue.|
|[Yarn.Compiler.Diagnostic.DiagnosticSeverity](/api/csharp/yarn.compiler.diagnostic.diagnosticseverity.md) severity|The severity of the issue.|

