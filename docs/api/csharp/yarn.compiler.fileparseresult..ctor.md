# FileParseResult(string,IParseTree,CommonTokenStream,IEnumerable<Diagnostic>)

Constructor in [FileParseResult](/docs/api/csharp/yarn.compiler.fileparseresult.md)

## Summary


Initializes a new instance of the  <a href="yarn.compiler.fileparseresult.md">FileParseResult</a> 
struct.


```csharp
public FileParseResult(string name, IParseTree tree, CommonTokenStream tokens, IEnumerable<Diagnostic> diagnostics)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the file.|
|`Antlr4.Runtime.Tree.IParseTree` tree|The parse tree extracted from the file.|
|`Antlr4.Runtime.CommonTokenStream` tokens|The tokens extracted from the file.|
|`System.Collections.Generic.IEnumerable<Yarn.Compiler.Diagnostic>` diagnostics|The diagnostics produced from parsing the file.|

