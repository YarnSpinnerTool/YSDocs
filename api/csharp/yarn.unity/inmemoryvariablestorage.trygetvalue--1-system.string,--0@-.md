# InMemoryVariableStorage.TryGetValue<T> Method

Retrieves a <see cref="!:Value"></see> by name.


```csharp
public override bool TryGetValue<T>(string variableName, out T result)
```

## Type Parameters
|Type Parameter|Description|
|:---|:---|
|T||
## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) variableName|The name of the variable to retrieve the value of. Don't forget to include the "$" at the beginning!|
|`T` result||
## Return Type
[`bool`](https://docs.microsoft.com/dotnet/api/System.Boolean): The <see cref="!:Value"></see>. If a variable by the name of
<code data-dev-comment-type="paramref" class="paramref">variableName</code> is not present, returns a value
representing `null`.



<div class="class-metadata">

Parent: [`InMemoryVariableStorage`](/api/csharp/yarn.unity/inmemoryvariablestorage.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/InMemoryVariableStorage.cs#L152), line 152.
