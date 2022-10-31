# MemoryVariableStore

Class in [Yarn](/api/csharp/yarn.md)

Inherits from `System.Object`

## Summary


A simple concrete implementation of  <a href="yarn.ivariablestorage.md">IVariableStorage</a> 
that keeps all variables in memory.


```csharp
public class MemoryVariableStore : IVariableStorage
```

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.memoryvariablestore.clear.md)|Removes all variables from storage.|
|[SetValue(string,bool)](/api/csharp/yarn.memoryvariablestore.setvalue-3.md)|Stores a  <code>bool</code>  in this VariableStorage.|
|[SetValue(string,float)](/api/csharp/yarn.memoryvariablestore.setvalue-2.md)|Stores a  <code>float</code>  in this VariableStorage.|
|[SetValue(string,string)](/api/csharp/yarn.memoryvariablestore.setvalue-1.md)|Stores a  <code>string</code>  in this VariableStorage.|
|[TryGetValue(string,T)](/api/csharp/yarn.memoryvariablestore.trygetvalue.md)|Retrieves a value of type  <code>T</code>  by name.|

