# Utility.TryGetNodeTitle(string?,YarnSpinnerParser.NodeContext,string?,string?,string?,string?)

Method in [Utility](/docs/api/csharp/yarn.compiler.utility.md)

## Summary


Gets the title for a node as defined in the source code, along with
its unique title (which may be different to the source title.)


```csharp
public static bool TryGetNodeTitle(string? sourceFileName, YarnSpinnerParser.NodeContext nodeContext, [System.Diagnostics.CodeAnalysis.NotNullWhen(true)] out string? sourceTitle, [System.Diagnostics.CodeAnalysis.NotNullWhen(true)] out string? uniqueTitle, out string? subtitle, out string? nodeGroupName)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` sourceFileName|The name of the file in which the node is defined, or  <code>null</code>  if not available.|
|`Yarn.Compiler.YarnSpinnerParser.NodeContext` nodeContext|The parsed node's context.|
|`string` sourceTitle|On return, contains the title of the node, as it appears in the source code.|
|`string` uniqueTitle|On return, contains the unique title of the node, as stored in the output program.|
|`string` subtitle|The sub-title of the node, if present. This value is always  <code>null</code>  if the node is not in a node group.|
|`string` nodeGroupName|The name of the node group the node is a member of, if any.|

## Returns

<code>true</code>  if the  <code>sourceTitle</code>  and  <code>uniqueTitle</code>  could be
determined;  <code>false</code>  otherwise.

