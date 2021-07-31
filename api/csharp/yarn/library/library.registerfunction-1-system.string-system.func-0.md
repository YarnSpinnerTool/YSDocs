# RegisterFunction&lt;TResult&gt;\(String, Func&lt;TResult&gt;\)

Registers a new function that returns a value, which can be called from a Yarn program.

```csharp
public void RegisterFunction<TResult>(string name, Func<TResult> implementation)
```

## Type Parameters

| Type Parameter | Description |
| :--- | :--- |
| TResult | The return type of the function. |

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) name | The name of the function. |
| [`Func{{TResult}}`](https://docs.microsoft.com/dotnet/api/System.Func{{TResult}}) implementation | The [`Func%601`](https://docs.microsoft.com/dotnet/api/System.Func%601) to be invoked when the function is called. |

## Exceptions

| Exception | Description |
| :--- | :--- |
| [`ArgumentException`](https://docs.microsoft.com/dotnet/api/System.ArgumentException) | Thrown when a function named `name` already exists in the [`Library`](./). |
|  |  |
| [`ArgumentNullException`](https://docs.microsoft.com/dotnet/api/System.ArgumentNullException) | Thrown when name is null. |
|  |  |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Library.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Library.cs#L72), line 72.

