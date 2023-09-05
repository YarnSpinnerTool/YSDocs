# InMemoryVariableStorage

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`VariableStorageBehaviour`](/api/csharp/yarn.unity.variablestoragebehaviour.md)

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
</pre> <p>Note that as of v2.0, this class no longer uses Yarn.Value, to
enforce static typing of declared variables within the Yarn
Program.</p>

## Fields

|Name|Description|
|:---|:---|
|[showDebug](/api/csharp/yarn.unity.inmemoryvariablestorage.showdebug.md)||

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.unity.inmemoryvariablestorage.clear.md)|Removes all variables from storage.|
|[Contains(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.contains.md)|returns a boolean value representing if the particular variable is inside the variable storage|
|[GetAllVariables()](/api/csharp/yarn.unity.inmemoryvariablestorage.getallvariables.md)||
|[GetDebugList()](/api/csharp/yarn.unity.inmemoryvariablestorage.getdebuglist.md)||
|[SetAllVariables(Dictionary<string, float>,Dictionary<string, string>,Dictionary<string, bool>,bool)](/api/csharp/yarn.unity.inmemoryvariablestorage.setallvariables.md)||
|[SetValue(string,bool)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-3.md)||
|[SetValue(string,float)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-2.md)||
|[SetValue(string,string)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-1.md)||
|[TryGetValue(string,T)](/api/csharp/yarn.unity.inmemoryvariablestorage.trygetvalue.md)|Retrieves a  <code>Yarn.Value</code>  by name.|

