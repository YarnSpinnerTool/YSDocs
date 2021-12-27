# InMemoryVariableStorage.TryGetValue(string,T)

Method in [InMemoryVariableStorage](/api/csharp/yarn.unity.inmemoryvariablestorage.md)

## Summary


Retrieves a  <code>Value</code>  by name.


```csharp
public override bool TryGetValue<T>(string variableName, out T result)
```

## Parameters

|Name|Description|
|:---|:---|
|variableName|The name of the variable to retrieve the value of. Don't forget to include the "$" at the beginning!|
|result||

## Returns

The  <code>Value</code> . If a variable by the name of
<code>variableName</code>  is not present, returns a value
representing `null`.

