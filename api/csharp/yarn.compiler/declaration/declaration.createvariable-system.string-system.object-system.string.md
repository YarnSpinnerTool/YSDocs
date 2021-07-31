# CreateVariable\(String, Object, String\)

Creates a new instance of the [`Declaration`](./) class, using the given `name` and default value. The [`ReturnType`](declaration.returntype.md) of the new instance will be configured based on the type of `defaultValue`, and the [`DeclarationType`](declaration.declarationtype.md) will be [`Variable`](../declaration.type/declaration.type.variable.md). All other properties will be their default values.

```csharp
public static Declaration CreateVariable(string name, object defaultValue, string description = null)
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) name | The name of the new declaration. |
| [`Object`](https://docs.microsoft.com/dotnet/api/System.Object) defaultValue | The default value of the declaration. This must be a string, a number \(integer or floating-point\), or boolean value. |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) description | The description of the new declaration. |

## Return Type

[`Declaration`](./): A new instance of the [`Declaration`](./) class.

## Namespace

[`Yarn.Compiler`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L192), line 192.

