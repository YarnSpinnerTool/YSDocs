# IVariableStorage

Interface in [Yarn](../)

## Summary

Provides a mechanism for storing and retrieving instances of the `Yarn.Value` class.

```csharp
public interface IVariableStorage
```

## Methods

| Name                                                           | Description                                |
| -------------------------------------------------------------- | ------------------------------------------ |
| [Clear()](yarn.ivariablestorage.clear.md)                      | Removes all variables from storage.        |
| [SetValue(string,bool)](yarn.ivariablestorage.setvalue-3.md)   | Stores a `bool` in this VariableStorage.   |
| [SetValue(string,float)](yarn.ivariablestorage.setvalue-2.md)  | Stores a `float` in this VariableStorage.  |
| [SetValue(string,string)](yarn.ivariablestorage.setvalue-1.md) | Stores a `string` in this VariableStorage. |
| [TryGetValue(string,T)](yarn.ivariablestorage.trygetvalue.md)  | Retrieves a value of type `T` by name.     |
