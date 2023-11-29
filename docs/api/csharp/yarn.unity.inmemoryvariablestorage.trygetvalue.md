# InMemoryVariableStorage.TryGetValue(string,T)

Method in [InMemoryVariableStorage](/api/csharp/yarn.unity.inmemoryvariablestorage.md)

## Summary


Retrieves a  <code>Yarn.Value</code>  by name.


```csharp
public override bool TryGetValue<T>(string variableName, out T result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` variableName|The name of the variable to retrieve the value of. Don't forget to include the "$" at the beginning!|
|`T` result||

## Returns

The  <code>Yarn.Value</code> . If a variable by the name of
<code>variableName</code>  is not present, returns a value
representing `null`.

