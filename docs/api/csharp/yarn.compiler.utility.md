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
|[AddTagsToLines(string,ICollection<string>?)](/docs/api/csharp/yarn.compiler.utility.addtagstolines.md)|Given Yarn source code, adds line tags to the ends of all lines that need one and do not already have one.|
|[DetermineNodeConnections(string[])](/docs/api/csharp/yarn.compiler.utility.determinenodeconnections.md)|Finds and collates every jump in every node.|
|[ExtractStringBlocks(IEnumerable<Node>,ProjectDebugInfo)](/docs/api/csharp/yarn.compiler.utility.extractstringblocks.md)|Gets the collection of contiguous runs of lines in the provided nodes. Each run of lines is guaranteed to run to completion once entered.|
|[GenerateYarnFileWithDeclarations(IEnumerable<Yarn.Compiler.Declaration>,string,IEnumerable<string>?,IDictionary<string, string>?)](/docs/api/csharp/yarn.compiler.utility.generateyarnfilewithdeclarations.md)|Generates a Yarn script that contains a node that declares variables.|
|[GetCompiledCodeAsString(Program,Library?,CompilationResult?)](/docs/api/csharp/yarn.compiler.utility.getcompiledcodeasstring.md)|Gets a string containing a representation of the compiled bytecode for a  <a href="yarn.program.md">Program</a> .|
|[GetYarnValue(IConvertible)](/docs/api/csharp/yarn.compiler.utility.getyarnvalue.md)|Returns an  <a href="yarn.iyarnvalue.md">IYarnValue</a>  representation of the provided value.|
|[ParseSource(string)](/docs/api/csharp/yarn.compiler.utility.parsesource.md)|Parses a string of Yarn source code, and produces a FileParseResult and (if there were any problems) a collection of diagnostics.|
|[TagLines(string,ICollection<string>?)](/docs/api/csharp/yarn.compiler.utility.taglines.md)|Given Yarn source code, adds line tags to the ends of all lines that need one and do not already have one.|
|[TryGetNodeTitle(string?,YarnSpinnerParser.NodeContext,string?,string?,string?,string?)](/docs/api/csharp/yarn.compiler.utility.trygetnodetitle.md)|Gets the title for a node as defined in the source code, along with its unique title (which may be different to the source title.)|

