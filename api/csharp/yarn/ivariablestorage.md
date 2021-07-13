# IVariableStorage Interface
Provides a mechanism for storing and retrieving instances
of the `Yarn.Value` class.

```csharp
public interface IVariableStorage
```



## Methods
|Name|Description|
|:---|:---|
|[`Clear()`](/api/csharp/yarn/ivariablestorage.clear.md)| Removes all variables from storage. |
|[`SetValue(String, Boolean)`](/api/csharp/yarn/ivariablestorage.setvalue-system.string,system.boolean-.md)| Stores a [`bool`](https://docs.microsoft.com/dotnet/api/System.Boolean) in this VariableStorage. |
|[`SetValue(String, Single)`](/api/csharp/yarn/ivariablestorage.setvalue-system.string,system.single-.md)| Stores a [`float`](https://docs.microsoft.com/dotnet/api/System.Single) in this VariableStorage. |
|[`SetValue(String, String)`](/api/csharp/yarn/ivariablestorage.setvalue-system.string,system.string-.md)| Stores a [`string`](https://docs.microsoft.com/dotnet/api/System.String) in this VariableStorage. |
|[`TryGetValue<T>(String, out T)`](/api/csharp/yarn/ivariablestorage.trygetvalue--1-system.string,--0@-.md)| Retrieves a `Yarn.Value` by name. |
## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L197), line 197.
