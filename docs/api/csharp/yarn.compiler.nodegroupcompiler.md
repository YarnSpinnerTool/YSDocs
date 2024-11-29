# NodeGroupCompiler

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary



```csharp
public class NodeGroupCompiler : ICodeEmitter
```

## Constructors

|Name|Description|
|:---|:---|
|[NodeGroupCompiler(string,IDictionary<string, Declaration>,IEnumerable<YarnSpinnerParser.NodeContext>,List<Node>)](/docs/api/csharp/yarn.compiler.nodegroupcompiler..ctor.md)|Initializes a new instance of the NodeGroupCompiler class.|

## Methods

|Name|Description|
|:---|:---|
|[Emit(IToken?,Instruction)](/docs/api/csharp/yarn.compiler.nodegroupcompiler.emit-1.md)|Creates a new instruction, and appends it to the current node in the <a href="yarn.program.md">Program</a> .|
|[Emit(IToken?,Instruction[])](/docs/api/csharp/yarn.compiler.nodegroupcompiler.emit-2.md)|Adds instructions to the current node in the  <a href="yarn.program.md">Program</a> .|
|[Emit(Instruction)](/docs/api/csharp/yarn.compiler.nodegroupcompiler.emit-3.md)|Creates a new instruction, and appends it to the current node in the <a href="yarn.program.md">Program</a> . Differs from the other Emit call by not requiring a start token. This enables its use in pure synthesised elements of the Yarn.|

## Properties

|Name|Description|
|:---|:---|
|[CompiledNodes](/docs/api/csharp/yarn.compiler.nodegroupcompiler.compilednodes.md)||
|[CurrentNode](/docs/api/csharp/yarn.compiler.nodegroupcompiler.currentnode.md)||
|[CurrentNodeDebugInfo](/docs/api/csharp/yarn.compiler.nodegroupcompiler.currentnodedebuginfo.md)||
|[NodeGroupName](/docs/api/csharp/yarn.compiler.nodegroupcompiler.nodegroupname.md)||
|[VariableDeclarations](/docs/api/csharp/yarn.compiler.nodegroupcompiler.variabledeclarations.md)||

