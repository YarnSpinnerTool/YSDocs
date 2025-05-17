# NodeDebugInfo

Class in [Yarn.Compiler](/docs/api/csharp/yarn.compiler.md)

Inherits from `System.Object`

## Summary


Contains debug information for a node in a Yarn file.


```csharp
public class NodeDebugInfo
```

## Constructors

|Name|Description|
|:---|:---|
|[NodeDebugInfo(string?,string)](/docs/api/csharp/yarn.compiler.nodedebuginfo..ctor.md)|Initialises a new instance of the NodeDebugInfo class.|

## Methods

|Name|Description|
|:---|:---|
|[GetLineInfo(int)](/docs/api/csharp/yarn.compiler.nodedebuginfo.getlineinfo.md)|Gets a  <a href="yarn.compiler.nodedebuginfo.lineinfo.md">LineInfo</a>  object that describes the specified instruction at the index  `instructionNumber` .|

## Properties

|Name|Description|
|:---|:---|
|[FileName](/docs/api/csharp/yarn.compiler.nodedebuginfo.filename.md)|Gets or sets the file that this DebugInfo was produced from.|
|[IsImplicit](/docs/api/csharp/yarn.compiler.nodedebuginfo.isimplicit.md)|Gets or sets a value indicating whether this node was created by the compiler.|
|[NodeName](/docs/api/csharp/yarn.compiler.nodedebuginfo.nodename.md)|Gets or sets the node that this DebugInfo was produced from.|
|[Range](/docs/api/csharp/yarn.compiler.nodedebuginfo.range.md)|The range in the file in which the node appears.|

## Structs

|Name|Description|
|:---|:---|
|[LineInfo](/docs/api/csharp/yarn.compiler.nodedebuginfo.lineinfo.md)|Contains positional information about an instruction.|

