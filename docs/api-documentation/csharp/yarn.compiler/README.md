# Yarn.Compiler Namespace

## Summary

Contains classes for compiling Yarn code.

## Classes

| Name                                                                              | Description                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [BasicBlock](yarn.compiler.basicblock/)                                           | A basic block is a run of instructions inside a Node. Basic blocks group instructions up into segments such that execution only ever begins at the start of a block (that is, a program never jumps into the middle of a block), and execution only ever leaves at the end of a block. |
| [Compiler](yarn.compiler.compiler/)                                               | Compiles Yarn code.                                                                                                                                                                                                                                                                    |
| [DebugInfo](yarn.compiler.debuginfo/)                                             | Contains debug information for a node in a Yarn file.                                                                                                                                                                                                                                  |
| [Declaration](yarn.compiler.declaration/)                                         | Represents a variable declaration                                                                                                                                                                                                                                                      |
| [DeclarationBuilder](yarn.compiler.declarationbuilder/)                           | Provides methods for constructing [Declaration](yarn.compiler.declaration/) objects.                                                                                                                                                                                                   |
| [DeferredTypeDiagnostic](yarn.compiler.deferredtypediagnostic/)                   | Represents a potential type error diagnostic message.                                                                                                                                                                                                                                  |
| [Diagnostic](yarn.compiler.diagnostic/)                                           | A diagnostic message that describes an error, warning or informational message that the user can take action on.                                                                                                                                                                       |
| [FunctionTypeBuilder](yarn.compiler.functiontypebuilder/)                         | Provides methods for constructing [FunctionType](../yarn/yarn.functiontype/) objects.                                                                                                                                                                                                  |
| [IndentAwareLexer](yarn.compiler.indentawarelexer/)                               | A Lexer subclass that detects newlines and generates indent and dedent tokens accordingly.                                                                                                                                                                                             |
| [InstructionCollectionExtensions](yarn.compiler.instructioncollectionextensions/) | Contains extension methods for producing [BasicBlock](yarn.compiler.basicblock/) objects from a Node.                                                                                                                                                                                  |
| [Position](yarn.compiler.position/)                                               | Represents a position in a multi-line string.                                                                                                                                                                                                                                          |
| [Project](yarn.compiler.project/)                                                 | Yarn Projects represent instructions on where to find Yarn scripts and associated assets, and how they should be compiled.                                                                                                                                                             |
| [Range](yarn.compiler.range/)                                                     | Represents a range of text in a multi-line string.                                                                                                                                                                                                                                     |
| [Utility](yarn.compiler.utility/)                                                 | Utility methods for working with line tags.                                                                                                                                                                                                                                            |

## Namespaces

| Name                                                 | Description                                                                       |
| ---------------------------------------------------- | --------------------------------------------------------------------------------- |
| [Yarn.Compiler.Upgrader](../yarn.compiler.upgrader/) | Contains classes for upgrading Yarn code to more recent versions of the language. |

## Structs

| Name                                                  | Description                                                                                    |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [CompilationJob](yarn.compiler.compilationjob/)       | An object that contains Yarn source code to compile, and instructions on how to compile it.    |
| [CompilationResult](yarn.compiler.compilationresult/) | The result of a compilation.                                                                   |
| [FileParseResult](yarn.compiler.fileparseresult/)     | Contains the result of parsing a single file of source code.                                   |
| [StringInfo](yarn.compiler.stringinfo/)               | Information about a string. Stored inside a string table, which is produced from the Compiler. |
