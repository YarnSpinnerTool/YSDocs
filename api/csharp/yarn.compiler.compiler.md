# Compiler

Class in [Yarn.Compiler](api/csharp/yarn.compiler.md)

Inherits from `Yarn.Compiler.YarnSpinnerParserBaseListener`

## Summary


Compiles Yarn code.


```csharp
public class Compiler : YarnSpinnerParserBaseListener
```

## Methods

|Name|Description|
|:---|:---|
|[Compile(CompilationJob)](api/csharp/yarn.compiler.compiler.compile.md)|Compiles Yarn code, as specified by a compilation job.|
|[FlattenParseTree(IParseTree)](api/csharp/yarn.compiler.compiler.flattenparsetree.md)|Flattens a tree of  <code>Antlr4.Runtime.Tree.IParseTree</code>  objects by recursively visiting their children, and converting them into a flat  <code>System.Collections.Generic.IEnumerable`1</code> .|
|[GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)](api/csharp/yarn.compiler.compiler.getdocumentcomments.md)|Gets the text of the documentation comments that either immediately precede  <code>context</code> , or are on the same line as <code>context</code> .|
|[GetLineIDForNodeName(string)](api/csharp/yarn.compiler.compiler.getlineidfornodename.md)||

