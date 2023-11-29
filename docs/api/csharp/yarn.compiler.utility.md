# Utility

Class in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Utility methods for working with line tags.


```csharp
public static class Utility
```

## Methods

|Name|Description|
|:---|:---|
|[AddTagsToLines(string,ICollection<string>)](/api/csharp/yarn.compiler.utility.addtagstolines.md)|Given Yarn source code, adds line tags to the ends of all lines that need one and do not already have one.|
|[DetermineNodeConnections(string[])](/api/csharp/yarn.compiler.utility.determinenodeconnections.md)|Finds and collates every jump in every node.|
|[ExtractStringBlocks(IEnumerable<Node>)](/api/csharp/yarn.compiler.utility.extractstringblocks.md)||
|[GenerateYarnFileWithDeclarations(IEnumerable<Yarn.Compiler.Declaration>,string,IEnumerable<string>,IDictionary<string, string>)](/api/csharp/yarn.compiler.utility.generateyarnfilewithdeclarations.md)|Generates a Yarn script that contains a node that declares variables.|
|[ParseSource(string)](/api/csharp/yarn.compiler.utility.parsesource.md)|Parses a string of Yarn source code, and produces a FileParseResult and (if there were any problems) a collection of diagnostics.|
|[TagLines(string,ICollection<string>)](/api/csharp/yarn.compiler.utility.taglines.md)|Given Yarn source code, adds line tags to the ends of all lines that need one and do not already have one.|

