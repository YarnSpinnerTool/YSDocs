# MemoryVariableStore.TryGetValue(string,T)

Method in [MemoryVariableStore](/api/csharp/yarn.memoryvariablestore.md)

## Summary


Retrieves a  <code>Yarn.Value</code>  by name.


```csharp
public bool TryGetValue<T>(string variableName, out T result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable to retrieve the value of.|
|`T` result||

## Returns

The  <code>Yarn.Value</code> . If a variable by the name of
`variableName` is not present, returns a value representing
`null`.

