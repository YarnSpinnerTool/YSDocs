# IVariableStorage

Interface in [Yarn](/api/csharp/yarn.md)

## Summary

Provides a mechanism for storing and retrieving instances
of the  <code>T:Yarn.Value</code>  class.

```csharp
public interface IVariableStorage
    {
    }
```

## Methods

|Name|Description|
|:---|:---|
|[SetValue(string,string)](/api/csharp/yarn.ivariablestorage.setvalue-1.md)|Stores a  <code>T:System.String</code>  in this VariableStorage.|
|[SetValue(string,float)](/api/csharp/yarn.ivariablestorage.setvalue-2.md)|Stores a  <code>T:System.Single</code>  in this VariableStorage.|
|[SetValue(string,bool)](/api/csharp/yarn.ivariablestorage.setvalue-3.md)|Stores a  <code>T:System.Boolean</code>  in this VariableStorage.|
|[TryGetValue(string,T)](/api/csharp/yarn.ivariablestorage.trygetvalue.md)|Retrieves a  <code>T:Yarn.Value</code>  by name.|
|[Clear()](/api/csharp/yarn.ivariablestorage.clear.md)|Removes all variables from storage.|

