# Yarn.Compiler Namespace

## Summary

Contains classes for compiling Yarn code.


## Classes

|Name|Description|
|:---|:---|
|[BasicBlock](api/csharp/yarn.compiler.basicblock.md)|A basic block is a run of instructions inside a Node. Basic blocks group instructions up into segments such that execution only ever begins at the start of a block (that is, a program never jumps into the middle of a block), and execution only ever leaves at the end of a block.|
|[Compiler](api/csharp/yarn.compiler.compiler.md)|Compiles Yarn code.|
|[DebugInfo](api/csharp/yarn.compiler.debuginfo.md)|Contains debug information for a node in a Yarn file.|
|[Declaration](api/csharp/yarn.compiler.declaration.md)||
|[DeclarationBuilder](api/csharp/yarn.compiler.declarationbuilder.md)|Provides methods for constructing  <a href="yarn.compiler.declaration.md">Declaration</a>  objects.|
|[DeferredTypeDiagnostic](api/csharp/yarn.compiler.deferredtypediagnostic.md)||
|[Diagnostic](api/csharp/yarn.compiler.diagnostic.md)|A diagnostic message that describes an error, warning or informational message that the user can take action on.|
|[FunctionTypeBuilder](api/csharp/yarn.compiler.functiontypebuilder.md)|Provides methods for constructing  <a href="yarn.functiontype.md">FunctionType</a>  objects.|
|[IndentAwareLexer](api/csharp/yarn.compiler.indentawarelexer.md)|A Lexer subclass that detects newlines and generates indent and dedent tokens accordingly.|
|[InstructionCollectionExtensions](api/csharp/yarn.compiler.instructioncollectionextensions.md)|Contains extension methods for producing  <a href="yarn.compiler.basicblock.md">BasicBlock</a>  objects from a Node.|
|[Position](api/csharp/yarn.compiler.position.md)|Represents a position in a multi-line string.|
|[Range](api/csharp/yarn.compiler.range.md)|Represents a range of text in a multi-line string.|
|[Utility](api/csharp/yarn.compiler.utility.md)|Utility methods for working with line tags.|

## Namespaces

|Name|Description|
|:---|:---|
|[Yarn.Compiler.Upgrader](api/csharp/yarn.compiler.upgrader.md)|Contains classes for upgrading Yarn code to more recent versions of the language.|

## Structs

|Name|Description|
|:---|:---|
|[CompilationJob](api/csharp/yarn.compiler.compilationjob.md)|An object that contains Yarn source code to compile, and instructions on how to compile it.|
|[CompilationResult](api/csharp/yarn.compiler.compilationresult.md)|The result of a compilation.|
|[FileParseResult](api/csharp/yarn.compiler.fileparseresult.md)|Contains the result of parsing a single file of source code.|
|[StringInfo](api/csharp/yarn.compiler.stringinfo.md)|Information about a string. Stored inside a string table, which is produced from the Compiler.|

