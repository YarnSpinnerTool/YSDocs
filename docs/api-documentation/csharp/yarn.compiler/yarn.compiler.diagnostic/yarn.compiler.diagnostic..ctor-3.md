# Diagnostic(string,ParserRuleContext,string,DiagnosticSeverity)

Constructor in [Diagnostic](./)

## Summary

Initializes a new instance of the [Diagnostic](./) class.

```csharp
public Diagnostic(string fileName, ParserRuleContext context, string message, DiagnosticSeverity severity = DiagnosticSeverity.Error)
```

## Parameters

| Name                                                                                                 | Description                                                         |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `string` fileName                                                                                    | Gets or sets the path, URI or file-name that the issue occurred in. |
| `Antlr4.Runtime.ParserRuleContext` context                                                           | The parse node at which the error occurred.                         |
| `string` message                                                                                     | Gets or sets the description of the issue.                          |
| [Yarn.Compiler.Diagnostic.DiagnosticSeverity](yarn.compiler.diagnostic.diagnosticseverity/) severity | Gets or sets the severity of the issue.                             |
