# Compiler

Class in [Yarn.Compiler](../)

Inherits from `Yarn.Compiler.YarnSpinnerParserBaseListener`

## Summary

Compiles Yarn code.

```csharp
public class Compiler : YarnSpinnerParserBaseListener
```

## Methods

| Name                                                                                                           | Description                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Compile(CompilationJob)](yarn.compiler.compiler.compile.md)                                                   | Compiles Yarn code, as specified by a compilation job.                                                                                                                             |
| [FlattenParseTree(IParseTree)](yarn.compiler.compiler.flattenparsetree.md)                                     | Flattens a tree of `Antlr4.Runtime.Tree.IParseTree` objects by recursively visiting their children, and converting them into a flat ``System.Collections.Generic.IEnumerable`1`` . |
| [GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)](yarn.compiler.compiler.getdocumentcomments.md) | Gets the text of the documentation comments that either immediately precede `context` , or are on the same line as `context` .                                                     |
| [GetLineIDForNodeName(string)](yarn.compiler.compiler.getlineidfornodename.md)                                 | Generates a line id for a raw text node                                                                                                                                            |
