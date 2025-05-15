# Compiler

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Compiles Yarn code.


```csharp
public static class Compiler
```

## Methods

|Name|Description|
|:---|:---|
|[Compile(CompilationJob)](/docs/api/csharp/yarn.compiler.compiler.compile.md)|Compiles Yarn code, as specified by a compilation job.|
|[FlattenParseTree(IParseTree)](/docs/api/csharp/yarn.compiler.compiler.flattenparsetree.md)|Flattens a tree of  `Antlr4.Runtime.Tree.IParseTree`  objects by recursively visiting their children, and converting them into a flat  `System.Collections.Generic.IEnumerable`1` .|
|[GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)](/docs/api/csharp/yarn.compiler.compiler.getdocumentcomments.md)|Gets the text of the documentation comments that either immediately precede  `context` , or are on the same line as `context` .|
|[GetLineIDForNodeName(string)](/docs/api/csharp/yarn.compiler.compiler.getlineidfornodename.md)|Generates a line id for a raw text node|

