# Type

Enum in [CompilationJob](../)

Inherits from `System.Enum`

## Summary

The type of compilation that the compiler will do.

```csharp
public enum Type
{
    FullCompilation,
    DeclarationsOnly,
    StringsOnly
}
```

## Members

| Name                                                                      | Description                                                                                                                                  |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| [DeclarationsOnly](yarn.compiler.compilationjob.type.declarationsonly.md) | The compiler will derive only the variable and function declarations, and file tags, found in the script.                                    |
| [FullCompilation](yarn.compiler.compilationjob.type.fullcompilation.md)   | The compiler will do a full compilation, and generate a [Program](../../../yarn/yarn.program/) , function declaration set, and string table. |
| [StringsOnly](yarn.compiler.compilationjob.type.stringsonly.md)           | The compiler will generate a string table only.                                                                                              |
