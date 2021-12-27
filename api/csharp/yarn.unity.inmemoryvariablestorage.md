# InMemoryVariableStorage

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`VariableStorageBehaviour`](/api/csharp/yarn.unity.variablestoragebehaviour.md)

## Summary


A simple implementation of VariableStorageBehaviour.


```csharp
public class InMemoryVariableStorage : VariableStorageBehaviour, IEnumerable<KeyValuePair<string, object>>
```

## Remarks


As of v2.0, this class has basic serialization and save/load
example functions. You can also enumerate over the variables by
using a `foreach` loop:

<![CDATA[```csharp    
// 'storage' is an InMemoryVariableStorage    
foreach (var variable in storage) {string name = variable.Key;
System.Object value = variable.Value;}   
```]]> 

Note that as of v2.0, this class no longer uses Yarn.Value, to
enforce static typing of declared variables within the Yarn
Program.


## Fields

|Name|Description|
|:---|:---|
|[showDebug](/api/csharp/yarn.unity.inmemoryvariablestorage.showdebug.md)||
|[TypeMappings](/api/csharp/yarn.unity.inmemoryvariablestorage.typemappings.md)||

## Methods

|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.unity.inmemoryvariablestorage.clear.md)|Removes all variables from storage.|
|[Contains(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.contains.md)|returns a boolean value representing if the particular variable is inside the variable storage|
|[DeserializeAllVariablesFromJSON(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.deserializeallvariablesfromjson.md)|Import a JSON string into variable storage, like when loading save game data.|
|[GetDebugList()](/api/csharp/yarn.unity.inmemoryvariablestorage.getdebuglist.md)||
|[LoadFromFile(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.loadfromfile.md)|Load JSON data from a file, then deserialize as variables.|
|[LoadFromPlayerPrefs()](/api/csharp/yarn.unity.inmemoryvariablestorage.loadfromplayerprefs-1.md)|Load JSON data from Unity's built-in PlayerPrefs with default playerPrefsKey, and deserialize as variables.|
|[LoadFromPlayerPrefs(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.loadfromplayerprefs-2.md)|Load JSON data from Unity's built-in PlayerPrefs with defined playerPrefsKey parameter, and deserialize as variables.|
|[SaveToFile(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.savetofile.md)|Serialize all variables to JSON, then write the data to a file.|
|[SaveToPlayerPrefs()](/api/csharp/yarn.unity.inmemoryvariablestorage.savetoplayerprefs-1.md)|Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs with default playerPrefsKey.|
|[SaveToPlayerPrefs(string)](/api/csharp/yarn.unity.inmemoryvariablestorage.savetoplayerprefs-2.md)|Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs under playerPrefsKey parameter.|
|[SerializeAllVariablesToJSON(bool)](/api/csharp/yarn.unity.inmemoryvariablestorage.serializeallvariablestojson.md)|Export variable storage to a JSON string, like when writing save game data.|
|[SetValue(string,bool)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-3.md)||
|[SetValue(string,float)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-2.md)||
|[SetValue(string,string)](/api/csharp/yarn.unity.inmemoryvariablestorage.setvalue-1.md)||
|[TryGetValue(string,T)](/api/csharp/yarn.unity.inmemoryvariablestorage.trygetvalue.md)|Retrieves a  <code>Value</code>  by name.|

