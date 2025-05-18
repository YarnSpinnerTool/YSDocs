# InMemoryVariableStorage

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`VariableStorageBehaviour`](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)

## Summary


A simple implementation of VariableStorageBehaviour.


```csharp
public class InMemoryVariableStorage : VariableStorageBehaviour, IEnumerable<KeyValuePair<string, object>>
```

## Remarks

<p>This class stores variables in memory, and is erased when the game
exits.</p> <p>This class also has basic serialization and save/load example functions.</p> <p>You can also enumerate over the variables by using a <code>foreach</code>
loop:</p> <pre lang="csharp">
// 'storage' is an InMemoryVariableStorage
foreach (var variable in storage) {
string name = variable.Key;
System.Object value = variable.Value;
}
</pre>

## Fields

|Name|Description|
|:---|:---|
|[showDebug](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.showdebug.md)||

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.clear.md)|Removes all variables from storage.|
|[Contains(string)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.contains.md)|returns a boolean value representing if the particular variable is inside the variable storage|
|[GetAllVariables()](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.getallvariables.md)||
|[GetDebugList()](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.getdebuglist.md)||
|[SetAllVariables(Dictionary<string, float>,Dictionary<string, string>,Dictionary<string, bool>,bool)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.setallvariables.md)||
|[SetValue(string,bool)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-3.md)||
|[SetValue(string,float)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-2.md)||
|[SetValue(string,string)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-1.md)||
|[TryGetValue<T>(string,T)](/docs/api/csharp/yarn.unity.inmemoryvariablestorage.trygetvalue.md)||

