# Diagnostic

Class in [Yarn.Compiler](yarn.compiler.md)

Inherits from `System.Object`

## Summary

A diagnostic message that describes an error, warning or informational\
message that the user can take action on.

```csharp
public sealed class Diagnostic
```

## Remarks

Diagnostics are presented to the user as the result of compilation,\
through the [CompilationResult](yarn.compiler.compilationresult.md) class's [Diagnostics](yarn.compiler.compilationresult.diagnostics.md) property.

## Constructors

| Name                                                                                                   | Description                                                                        |
| ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| [Diagnostic(string,IToken,string,DiagnosticSeverity)](yarn.compiler.diagnostic..ctor-4.md)             | Initializes a new instance of the [Diagnostic](yarn.compiler.diagnostic.md) class. |
| [Diagnostic(string,ParserRuleContext?,string,DiagnosticSeverity)](yarn.compiler.diagnostic..ctor-3.md) | Initializes a new instance of the [Diagnostic](yarn.compiler.diagnostic.md) class. |
| [Diagnostic(string,string,DiagnosticSeverity)](yarn.compiler.diagnostic..ctor-1.md)                    | Initializes a new instance of the [Diagnostic](yarn.compiler.diagnostic.md) class. |
| [Diagnostic(string,DiagnosticSeverity)](yarn.compiler.diagnostic..ctor-2.md)                           | Initializes a new instance of the [Diagnostic](yarn.compiler.diagnostic.md) class. |
| [Diagnostic(string,Range,string,DiagnosticSeverity)](yarn.compiler.diagnostic..ctor-5.md)              | Initializes a new instance of the [Diagnostic](yarn.compiler.diagnostic.md) class. |

## Enums

| Name                                                                 | Description                |
| -------------------------------------------------------------------- | -------------------------- |
| [DiagnosticSeverity](yarn.compiler.diagnostic.diagnosticseverity.md) | The severity of the issue. |

## Methods

| Name                                                     | Description |
| -------------------------------------------------------- | ----------- |
| [Equals(object)](yarn.compiler.diagnostic.equals.md)     |             |
| [GetHashCode()](yarn.compiler.diagnostic.gethashcode.md) |             |
| [ToString()](yarn.compiler.diagnostic.tostring.md)       |             |

## Properties

| Name                                             | Description                                                                                                                  |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| [Column](yarn.compiler.diagnostic.column.md)     | Gets the zero-indexed character number in FileName at which the issue begins.                                                |
| [Context](yarn.compiler.diagnostic.context.md)   | Gets or sets the source text of [FileName](yarn.compiler.diagnostic.filename.md) containing the issue.                       |
| [FileName](yarn.compiler.diagnostic.filename.md) | Gets or sets the path, URI or file-name that the issue occurred in.                                                          |
| [Line](yarn.compiler.diagnostic.line.md)         | Gets the zero-indexed line number in FileName at which the issue begins.                                                     |
| [Message](yarn.compiler.diagnostic.message.md)   | Gets or sets the description of the issue.                                                                                   |
| [Range](yarn.compiler.diagnostic.range.md)       | Gets or sets the range of the file indicated by [FileName](yarn.compiler.diagnostic.filename.md) that the issue occurred in. |
| [Severity](yarn.compiler.diagnostic.severity.md) | Gets or sets the severity of the issue.                                                                                      |
