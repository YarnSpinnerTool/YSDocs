# MemoryVariableStore

Class in [Yarn](yarn.md)

Inherits from `System.Object`

## Summary

A simple concrete implementation of [IVariableStorage](yarn.ivariablestorage.md) that keeps all variables in memory.

```csharp
public class MemoryVariableStore : IVariableStorage
```

## Methods

| Name                                                              | Description                                |
| ----------------------------------------------------------------- | ------------------------------------------ |
| [Clear()](yarn.memoryvariablestore.clear.md)                      | Removes all variables from storage.        |
| [SetValue(string,bool)](yarn.memoryvariablestore.setvalue-3.md)   | Stores a `bool` in this VariableStorage.   |
| [SetValue(string,float)](yarn.memoryvariablestore.setvalue-2.md)  | Stores a `float` in this VariableStorage.  |
| [SetValue(string,string)](yarn.memoryvariablestore.setvalue-1.md) | Stores a `string` in this VariableStorage. |
| [TryGetValue(string,T)](yarn.memoryvariablestore.trygetvalue.md)  | Retrieves a value of type `T` by name.     |
