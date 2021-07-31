# RegisterFunction&lt;T1, T2, T3, T4, TResult&gt;\(String, Func&lt;T1, T2, T3, T4, TResult&gt;\)

```csharp
public void RegisterFunction<T1, T2, T3, T4, TResult>(string name, Func<T1, T2, T3, T4, TResult> implementation)
```

## Type Parameters

| Type Parameter | Description |
| :--- | :--- |
| T1 | The type of the function's first argument. |
| T2 | The type of the function's second argument. |
| T3 | The type of the function's third argument. |
| T4 | The type of the function's fourth argument. |
| TResult | The return type of the function. |

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) name |  |
| [`Func{{T1},{T2},{T3},{T4},{TResult}}`](https://docs.microsoft.com/dotnet/api/System.Func{{T1},{T2},{T3},{T4},{TResult}}) implementation |  |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Library.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Library.cs#L110), line 110.

