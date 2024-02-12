# TryGetValue(string,T)

Method in [InMemoryVariableStorage](./)

## Summary

Retrieves a `Yarn.Value` by name.

```csharp
public override bool TryGetValue<T>(string variableName, out T result)
```

## Parameters

| Name                  | Description                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------- |
| `string` variableName | The name of the variable to retrieve the value of. Don't forget to include the "$" at the beginning! |
| `T` result            |                                                                                                      |

## Returns

The `Yarn.Value` . If a variable by the name of `variableName` is not present, returns a value representing `null`.
