# FileParseResult

Struct in [Yarn.Compiler](/api/csharp/yarn.compiler.md)

Inherits from `System.ValueType`

## Summary


Contains the result of parsing a single file of source code.


```csharp
public struct FileParseResult
```

## Remarks


This class provides only syntactic information about a parse - that is,
it provides access to the parse tree, and the stream of tokens used to
produce that parse tree.


## Properties

|Name|Description|
|:---|:---|
|[Name](/api/csharp/yarn.compiler.fileparseresult.name.md)|<param name="name">The name of the file.</param>|
|[Tokens](/api/csharp/yarn.compiler.fileparseresult.tokens.md)|<param name="tokens">The tokens extracted from the file.</param>|
|[Tree](/api/csharp/yarn.compiler.fileparseresult.tree.md)|<param name="tree">The parse tree extracted from the file.</param>|

## Methods

|Name|Description|
|:---|:---|
|[FileParseResult(string,IParseTree,CommonTokenStream)](/api/csharp/yarn.compiler.fileparseresult..ctor.md)|Initializes a new instance of the  <a href="yarn.compiler.fileparseresult.md">FileParseResult</a>  struct.|
|[Equals(object)](/api/csharp/yarn.compiler.fileparseresult.equals.md)||
|[GetHashCode()](/api/csharp/yarn.compiler.fileparseresult.gethashcode.md)||

