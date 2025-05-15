# MemoryVariableStore.TryGetValue(string,T?)

Method in [MemoryVariableStore](/docs/api/csharp/yarn.memoryvariablestore.md)

## Summary


Given a variable name, attempts to fetch a value for the variable,
either from storage, initial values found in  [Program](yarn.ivariableaccess.program.md) ,
or by evaluating a smart variable found in  [Program](yarn.ivariableaccess.program.md) .


```csharp
public virtual bool TryGetValue<T>(string variableName, [System.Diagnostics.CodeAnalysis.NotNullWhen(true)] out T? result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable.|
|`T` result|If this method returns  `true` , this parameter will contain the fetched value.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the value to return. The fetched value will be converted to this type, if possible.|

## Returns

`true`  if a value could be fetched;  `false`  otherwise.

