# TryGetValue&lt;T&gt;\(String, out T\)

Retrieves a `Yarn.Value` by name.

```csharp
bool TryGetValue<T>(string variableName, out T result)
```

## Type Parameters

| Type Parameter | Description |
| :--- | :--- |
| T |  |

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) variableName | The name of the variable to retrieve the value of. |
| `T` result |  |

## Return Type

[`bool`](https://docs.microsoft.com/dotnet/api/System.Boolean): The `Yarn.Value`. If a variable by the name of `variableName` is not present, returns a value representing `null`.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L231), line 231.

