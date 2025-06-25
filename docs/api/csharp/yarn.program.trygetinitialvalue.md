# TryGetInitialValue\<T>(string,T)

Method in [Program](yarn.program.md)

## Summary

Attempts to fetch a value for a variable named `variableName` from this program's collection of initial\
values.

```csharp
public bool TryGetInitialValue<T>(string variableName, out T result)
```

## Parameters

| Name                  | Description                                                                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `string` variableName | The name of the variable to retrieve a value for.                                                                                             |
| `T` result            | On return, contains the value of the variable, or the default value of `T` if not known. Depending on what `T` is, this value may be `null` . |

## Type Parameters

| Name | Description                       |
| ---- | --------------------------------- |
| T    | The type of variable to retrieve. |

## Returns

`true` if an initial value for `variableName` was found; `false`\
otherwise.
