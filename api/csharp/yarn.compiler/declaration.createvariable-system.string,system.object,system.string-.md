# Declaration.CreateVariable Method

Creates a new instance of the [`Declaration`](/api/csharp/yarn.compiler/declaration.md) class,
using the given <code data-dev-comment-type="paramref" class="paramref">name</code> and default value. The
[`ReturnType`](/api/csharp/yarn.compiler/declaration.returntype.md) of the new instance will be configured
based on the type of <code data-dev-comment-type="paramref" class="paramref">defaultValue</code>, and the
[`DeclarationType`](/api/csharp/yarn.compiler/declaration.declarationtype.md) will be [`Variable`](/api/csharp/yarn.compiler/declaration.type.variable.md). All other properties will be their
default values.


```csharp
public static Declaration CreateVariable(string name, object defaultValue, string description = null)
```

## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) name|The name of the new declaration.|
|[`Object`](https://docs.microsoft.com/dotnet/api/System.Object) defaultValue|The default value of the declaration. This must be a string, a number (integer or floating-point), or boolean value.|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) description|The description of the new declaration.|
## Return Type
[`Declaration`](/api/csharp/yarn.compiler/declaration.md): A new instance of the [`Declaration`](/api/csharp/yarn.compiler/declaration.md)
class.



## Namespace
[`Yarn.Compiler`](/api/csharp/yarn.compiler/README.md)

## Assembly
YarnSpinner.Compiler.dll

## Source
Defined in [YarnSpinner.Compiler/Compiler.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Compiler.cs#L192), line 192.
