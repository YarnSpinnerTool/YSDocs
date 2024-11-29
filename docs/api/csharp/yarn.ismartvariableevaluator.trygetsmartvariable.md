# ISmartVariableEvaluator.TryGetSmartVariable(string,T)

Method in [ISmartVariableEvaluator](/docs/api/csharp/yarn.ismartvariableevaluator.md)

## Summary


Evaluate the value of a smart variable named  <code>name</code> .


```csharp
bool TryGetSmartVariable<T>(string name, out T result);
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the variable.|
|`T` result|On return, contains the returned value of the smart variable, or the  <code>default</code>  value of <code>T</code>  if a smart variable named  <code>name</code>  could not be found or its value could not be returned as type  <code>T</code> .|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the returned value.|

## Returns

<code>true</code>  if the smart variable was evaluated,
<code>false</code>  otherwise.

