# NodeGroupCompiler(string,IDictionary<string, Declaration>,IEnumerable<YarnSpinnerParser.NodeContext>,List<Node>)

Constructor in [NodeGroupCompiler](/docs/api/csharp/yarn.compiler.nodegroupcompiler.md)

## Summary


Initializes a new instance of the NodeGroupCompiler class.


```csharp
public NodeGroupCompiler(string nodeGroupName, IDictionary<string, Declaration> variableDeclarations, IEnumerable<YarnSpinnerParser.NodeContext> nodeContexts, List<Node> compiledNodes)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeGroupName|The name of the node group to compile.|
|`System.Collections.Generic.IDictionary<string, Yarn.Compiler.Declaration>` variableDeclarations|The collection of existing variable declarations found during compilation.|
|`System.Collections.Generic.IEnumerable<Yarn.Compiler.YarnSpinnerParser.NodeContext>` nodeContexts|The collection of node group parser contexts that all belong to this node group.|
|`System.Collections.Generic.List<Yarn.Node>` compiledNodes||

