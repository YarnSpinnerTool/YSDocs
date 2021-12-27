# Type

Enum in [CompilationJob](/api/csharp/yarn.compiler.compilationjob.md)

Inherits from `System.Enum`

## Summary



```csharp
public enum Type
{
    FullCompilation,
    DeclarationsOnly,
    StringsOnly
}
```

## Fields

|Name|Description|
|:---|:---|
|[DeclarationsOnly](/api/csharp/yarn.compiler.compilationjob.type.declarationsonly.md)|The compiler will derive only the variable and function declarations, and file tags, found in the script.|
|[FullCompilation](/api/csharp/yarn.compiler.compilationjob.type.fullcompilation.md)|The compiler will do a full compilation, and generate a  <a href="yarn.program.md">Program</a> , function declaration set, and string table.|
|[StringsOnly](/api/csharp/yarn.compiler.compilationjob.type.stringsonly.md)|The compiler will generate a string table only.|

