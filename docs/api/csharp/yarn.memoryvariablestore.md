# MemoryVariableStore

Class in [Yarn](yarn.md)

Inherits from `System.Object`

## Summary

A simple concrete implementation of [IVariableStorage](yarn.ivariablestorage.md) that keeps all variables in memory.

```csharp
public class MemoryVariableStore : IVariableStorage
```

## Methods

| Name                                                                   | Description                                |
| ---------------------------------------------------------------------- | ------------------------------------------ |
| [Clear()](yarn.memoryvariablestore.clear.md)                           | Removes all variables from storage.        |
| [GetVariableKind(string)](yarn.memoryvariablestore.getvariablekind.md) |                                            |
| [SetValue(string,bool)](yarn.memoryvariablestore.setvalue-3.md)        | Stores a `bool` in this VariableStorage.   |
| [SetValue(string,float)](yarn.memoryvariablestore.setvalue-2.md)       | Stores a `float` in this VariableStorage.  |
| [SetValue(string,string)](yarn.memoryvariablestore.setvalue-1.md)      | Stores a `string` in this VariableStorage. |
| [TryGetValue(string,T)](yarn.memoryvariablestore.trygetvalue.md)       |                                            |

## Properties

| Name                                                                         | Description                                                                                                                                                                        |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Program](yarn.memoryvariablestore.program.md)                               | Gets or sets the Yarn [Program](yarn.ivariableaccess.program.md) that stores information about the initial values of variables, and is able to produce values for smart variables. |
| [SmartVariableEvaluator](yarn.memoryvariablestore.smartvariableevaluator.md) | Gets or sets the object to use when evaluating smart variables.                                                                                                                    |
