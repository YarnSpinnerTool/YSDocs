# FileParseResult

Struct in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary


Contains the result of parsing a single file of source code.


```csharp
public struct FileParseResult : ISourceInput
```

## Remarks


This class provides only syntactic information about a parse - that is,
it provides access to the parse tree, and the stream of tokens used to
produce that parse tree.


## Constructors

|Name|Description|
|:---|:---|
|[FileParseResult(string,IParseTree,CommonTokenStream,IEnumerable<Diagnostic>)](/docs/api/csharp/yarn.compiler.fileparseresult..ctor.md)|Initializes a new instance of the  <a href="yarn.compiler.fileparseresult.md">FileParseResult</a>  struct.|

## Methods

|Name|Description|
|:---|:---|
|[Equals(object)](/docs/api/csharp/yarn.compiler.fileparseresult.equals.md)||
|[GetHashCode()](/docs/api/csharp/yarn.compiler.fileparseresult.gethashcode.md)||

## Properties

|Name|Description|
|:---|:---|
|[Diagnostics](/docs/api/csharp/yarn.compiler.fileparseresult.diagnostics.md)|<param name="tokens">The tokens extracted from the file.</param>|
|[FileName](/docs/api/csharp/yarn.compiler.fileparseresult.filename.md)|The name of the input.|
|[Name](/docs/api/csharp/yarn.compiler.fileparseresult.name.md)|<param name="name">The name of the file.</param>|
|[Tokens](/docs/api/csharp/yarn.compiler.fileparseresult.tokens.md)|<param name="tokens">The tokens extracted from the file.</param>|
|[Tree](/docs/api/csharp/yarn.compiler.fileparseresult.tree.md)|<param name="tree">The parse tree extracted from the file.</param>|

