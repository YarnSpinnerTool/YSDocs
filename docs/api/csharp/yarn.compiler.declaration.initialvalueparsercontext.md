# InitialValueParserContext

Property in [Declaration](yarn.compiler.declaration.md)

## Summary

Gets or sets the parser context for the initial value provided in this variable's 'declare' statement, if any. This is only valid for variable declarations, not functions (because functions don't have a value.)

```csharp
public YarnSpinnerParser.ExpressionContext? InitialValueParserContext { get; set; }
```
