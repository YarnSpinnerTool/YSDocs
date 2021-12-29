# Compiler

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `Yarn.Compiler.YarnSpinnerParserBaseListener`

## Summary


Compiles Yarn code.


```csharp
public class Compiler : YarnSpinnerParserBaseListener
```

## Methods

|Name|Description|
|:---|:---|
|[Compile(CompilationJob)](/api/csharp/yarn.compiler.compiler.compile.md)||
|[FlattenParseTree(IParseTree)](/api/csharp/yarn.compiler.compiler.flattenparsetree.md)|Flattens a tree of  <code>Antlr4.Runtime.Tree.IParseTree</code>  objects by recursively visiting their children, and converting them into a flat  <code>System.Collections.Generic.IEnumerable`1</code> .|
|[GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)](/api/csharp/yarn.compiler.compiler.getdocumentcomments.md)||
|[GetLineIDForNodeName(string)](/api/csharp/yarn.compiler.compiler.getlineidfornodename.md)||

