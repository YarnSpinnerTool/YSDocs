# Type

Enum in [CompilationJob](/docs/api/csharp/yarn.compiler.compilationjob.md)

Inherits from `System.Enum`

## Summary


The type of compilation that the compiler will do.


```csharp
public enum Type
{
    FullCompilation,
    TypeCheck,
    DeclarationsOnly = TypeCheck,
    StringsOnly
}
```

## Members

|Name|Description|
|:---|:---|
|[DeclarationsOnly](/docs/api/csharp/yarn.compiler.compilationjob.type.declarationsonly.md)|Generate declarations only. This is equivalent to  <a href="yarn.compiler.compilationjob.type.typecheck.md">TypeCheck</a> .|
|[FullCompilation](/docs/api/csharp/yarn.compiler.compilationjob.type.fullcompilation.md)|The compiler will do a full compilation, and generate a  <a href="yarn.program.md">Program</a> , function declaration set, and string table.|
|[StringsOnly](/docs/api/csharp/yarn.compiler.compilationjob.type.stringsonly.md)|The compiler will generate a string table only.|
|[TypeCheck](/docs/api/csharp/yarn.compiler.compilationjob.type.typecheck.md)|The compiler will derive only the variable and function declarations, and file tags, found in the script.|

