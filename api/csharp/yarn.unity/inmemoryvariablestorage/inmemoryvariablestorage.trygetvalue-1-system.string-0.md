# TryGetValue&lt;T&gt;\(String, out T\)

Retrieves a  by name.

```csharp
public override bool TryGetValue<T>(string variableName, out T result)
```

## Type Parameters

| Type Parameter | Description |
| :--- | :--- |
| T |  |

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) variableName | The name of the variable to retrieve the value of. Don't forget to include the "$" at the beginning! |
| `T` result |  |

## Return Type

[`bool`](https://docs.microsoft.com/dotnet/api/System.Boolean): The . If a variable by the name of `variableName` is not present, returns a value representing `null`.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/InMemoryVariableStorage.cs#L152), line 152.

