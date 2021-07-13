# Program Class

A compiled Yarn program.


```csharp
public sealed class Program : IMessage<Program>, IMessage, IEquatable<Program>, IDeepCloneable<Program>
```



## Methods
|Name|Description|
|:---|:---|
|[`Combine(Program[])`](/api/csharp/yarn/program.combine-program---.md)| Creates a new Program by merging multiple Programs together. |
## Properties
|Name|Description|
|:---|:---|
|[`InitialValues`](/api/csharp/yarn/program.initialvalues.md)| The collection of initial values for variables; if a PUSH_VARIABLE instruction is run, and the value is not found in the storage, this value will be used |
|[`Name`](/api/csharp/yarn/program.name.md)| The name of the program. |
|[`Nodes`](/api/csharp/yarn/program.nodes.md)| The collection of nodes in this program. |
<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L64), line 64.
