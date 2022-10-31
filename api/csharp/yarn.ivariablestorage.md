# IVariableStorage

Interface in [Yarn](api/csharp/yarn.md)

## Summary

Provides a mechanism for storing and retrieving instances
of the  <code>Yarn.Value</code>  class.

```csharp
public interface IVariableStorage
```

## Methods

|Name|Description|
|:---|:---|
|[Clear()](api/csharp/yarn.ivariablestorage.clear.md)|Removes all variables from storage.|
|[SetValue(string,bool)](api/csharp/yarn.ivariablestorage.setvalue-3.md)|Stores a  <code>bool</code>  in this VariableStorage.|
|[SetValue(string,float)](api/csharp/yarn.ivariablestorage.setvalue-2.md)|Stores a  <code>float</code>  in this VariableStorage.|
|[SetValue(string,string)](api/csharp/yarn.ivariablestorage.setvalue-1.md)|Stores a  <code>string</code>  in this VariableStorage.|
|[TryGetValue(string,T)](api/csharp/yarn.ivariablestorage.trygetvalue.md)|Retrieves a value of type  <code>T</code>  by name.|

