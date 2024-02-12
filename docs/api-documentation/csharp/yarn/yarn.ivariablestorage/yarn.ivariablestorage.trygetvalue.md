# TryGetValue(string,T)

Method in [IVariableStorage](./)

## Summary

Retrieves a value of type `T` by name.

```csharp
bool TryGetValue<T>(string variableName, out T result);
```

## Parameters

| Name                  | Description                                                                                                                                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `string` variableName | The name of the variable to retrieve the value of.                                                                                                                                                            |
| `T` result            | On return, if this method returned true, contains the retrieved value. If this method returned false, contains the default value of `T` (for example, `0` for `float` values, `null` for strings, and so on.) |

## Type Parameters

| Name | Description                           |
| ---- | ------------------------------------- |
| T    | The type of the variable to retrieve. |

## Returns

`true` if a value named `variableName` of type `T` was retrieved; `false` otherwise.
