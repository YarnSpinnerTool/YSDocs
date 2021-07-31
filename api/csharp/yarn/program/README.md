# Program

A compiled Yarn program.

```csharp
public sealed class Program : IMessage<Program>, IMessage, IEquatable<Program>, IDeepCloneable<Program>
```

## Methods

| Name | Description |
| :--- | :--- |
| [`Combine(Program[])`](program.combine-program.md) | Creates a new Program by merging multiple Programs together. |

## Properties

| Name | Description |
| :--- | :--- |
| [`InitialValues`](program.initialvalues.md) | The collection of initial values for variables; if a PUSH\_VARIABLE instruction is run, and the value is not found in the storage, this value will be used |
| [`Name`](program.name.md) | The name of the program. |
| [`Nodes`](program.nodes.md) | The collection of nodes in this program. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L64), line 64.

