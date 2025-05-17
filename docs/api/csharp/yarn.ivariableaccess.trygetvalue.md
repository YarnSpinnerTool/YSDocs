# IVariableAccess.TryGetValue(string,T?)

Method in [IVariableAccess](/docs/api/csharp/yarn.ivariableaccess.md)

## Summary


Given a variable name, attempts to fetch a value for the variable,
either from storage, initial values found in  <a href="yarn.ivariableaccess.program.md">Program</a> ,
or by evaluating a smart variable found in  <a href="yarn.ivariableaccess.program.md">Program</a> .


```csharp
bool TryGetValue<T>(string variableName, [System.Diagnostics.CodeAnalysis.NotNullWhen(true)] out T? result);
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable.|
|`T` result|If this method returns  <code>true</code> , this parameter will contain the fetched value.|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the value to return. The fetched value will be converted to this type, if possible.|

## Returns

<code>true</code>  if a value could be fetched;  <code>false</code>  otherwise.

