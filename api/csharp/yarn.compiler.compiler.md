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
|[EnterBody(YarnSpinnerParser.BodyContext)](/api/csharp/yarn.compiler.compiler.enterbody.md)||
|[EnterNode(YarnSpinnerParser.NodeContext)](/api/csharp/yarn.compiler.compiler.enternode.md)||
|[ExitBody(YarnSpinnerParser.BodyContext)](/api/csharp/yarn.compiler.compiler.exitbody.md)||
|[ExitHeader(YarnSpinnerParser.HeaderContext)](/api/csharp/yarn.compiler.compiler.exitheader.md)||
|[ExitNode(YarnSpinnerParser.NodeContext)](/api/csharp/yarn.compiler.compiler.exitnode.md)||
|[FlattenParseTree(IParseTree)](/api/csharp/yarn.compiler.compiler.flattenparsetree.md)|Flattens a tree of  <code>Antlr4.Runtime.Tree.IParseTree</code>  objects by recursively visiting their children, and converting them into a flat  <code>System.Collections.Generic.IEnumerable`1</code> .|
|[GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)](/api/csharp/yarn.compiler.compiler.getdocumentcomments.md)||
|[GetLineIDForNodeName(string)](/api/csharp/yarn.compiler.compiler.getlineidfornodename.md)||

