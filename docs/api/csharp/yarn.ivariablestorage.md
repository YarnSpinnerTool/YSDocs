# IVariableStorage

Interface in [Yarn](/docs/api/csharp/yarn.md)

## Summary

Provides a mechanism for storing and retrieving instances
of the  <code>Yarn.Value</code>  class.

```csharp
public interface IVariableStorage
```

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/docs/api/csharp/yarn.ivariablestorage.clear.md)|Removes all variables from storage.|
|[SetValue(string,bool)](/docs/api/csharp/yarn.ivariablestorage.setvalue-3.md)|Stores a  <code>bool</code>  in this VariableStorage.|
|[SetValue(string,float)](/docs/api/csharp/yarn.ivariablestorage.setvalue-2.md)|Stores a  <code>float</code>  in this VariableStorage.|
|[SetValue(string,string)](/docs/api/csharp/yarn.ivariablestorage.setvalue-1.md)|Stores a  <code>string</code>  in this VariableStorage.|
|[TryGetValue(string,T)](/docs/api/csharp/yarn.ivariablestorage.trygetvalue.md)|Retrieves a value of type  <code>T</code>  by name.|

