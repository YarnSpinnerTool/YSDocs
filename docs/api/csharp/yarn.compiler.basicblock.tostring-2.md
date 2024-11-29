# BasicBlock.ToString(Library?,CompilationResult?)

Method in [BasicBlock](/docs/api/csharp/yarn.compiler.basicblock.md)

## Summary


Gets a string containing the textual description of the instructions
in this  <a href="yarn.compiler.basicblock.md">BasicBlock</a> .


```csharp
public string ToString(Library? library, CompilationResult? compilationResult)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Library](/docs/api/csharp/yarn.library.md) library|The  <a href="yarn.library.md">Library</a>  to use when converting instructions to strings.|
|[Yarn.Compiler.CompilationResult](/docs/api/csharp/yarn.compiler.compilationresult.md) compilationResult|The  <a href="yarn.compiler.compilationresult.md">CompilationResult</a>  that produced  <a href="yarn.compiler.basicblock.node.md">Node</a> .|

## Returns

A string containing the text version of the
instructions.

