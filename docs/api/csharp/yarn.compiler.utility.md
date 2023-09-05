# Utility

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Utility methods for working with line tags.


```csharp
public static class Utility
```

## Methods

|Name|Description|
|:---|:---|
|[AddTagsToLines(string,ICollection<string>)](/docs/api/csharp/yarn.compiler.utility.addtagstolines.md)|Given Yarn source code, adds line tags to the ends of all lines that need one and do not already have one.|
|[DetermineNodeConnections(string[])](/docs/api/csharp/yarn.compiler.utility.determinenodeconnections.md)|Finds and collates every jump in every node.|
|[ExtractStringBlocks(IEnumerable<Node>)](/docs/api/csharp/yarn.compiler.utility.extractstringblocks.md)||
|[GenerateYarnFileWithDeclarations(IEnumerable<Yarn.Compiler.Declaration>,string,IEnumerable<string>,IDictionary<string, string>)](/docs/api/csharp/yarn.compiler.utility.generateyarnfilewithdeclarations.md)|Generates a Yarn script that contains a node that declares variables.|
|[ParseSource(string)](/docs/api/csharp/yarn.compiler.utility.parsesource.md)|Parses a string of Yarn source code, and produces a FileParseResult and (if there were any problems) a collection of diagnostics.|

