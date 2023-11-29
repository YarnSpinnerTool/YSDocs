# MemoryVariableStore.TryGetValue(string,T)

Method in [MemoryVariableStore](/api/csharp/yarn.memoryvariablestore.md)

## Summary


Retrieves a value of type  <code>T</code>  by name.


```csharp
public bool TryGetValue<T>(string variableName, out T result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable to retrieve the value of.|
|`T` result|On return, if this method returned true, contains the retrieved value. If this method returned false, contains the default value of  <code>T</code>  (for example, <code>0</code>  for  <code>float</code>  values,  <code>null</code>  for strings, and so on.)|

## Type Parameters

|Name|Description|
|:---|:---|
|T|The type of the variable to retrieve.|

## Returns

<code>true</code>  if a value named  <code>variableName</code>  of type  <code>T</code>  was
retrieved;  <code>false</code>  otherwise.

