# CompilationResult.StringTable

Property in [CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md)

## Summary


Gets a dictionary mapping line IDs to StringInfo objects.


```csharp
public IDictionary<string, StringInfo>? StringTable { get; internal set; }
```

## Remarks


The string table contains the extracted line text found in the
provided source code. The keys of this dictionary are the line IDs
for each line - either through explicit line tags indicated through
the  <code>#line:</code>  tag, or implicitly-generated line IDs that the
compiler added during compilation.


