# InMemoryVariableStorage Class

A simple implementation of VariableStorageBehaviour.


```csharp
public class InMemoryVariableStorage : VariableStorageBehaviour, IVariableStorage, IEnumerable<KeyValuePair<string, object>>
```
## Remarks

As of v2.0, this class has basic serialization and save/load example functions.
You can also enumerate over the variables by using a `foreach` loop:


```csharp    
// 'storage' is an InMemoryVariableStorage    
foreach (var variable in storage) {
    string name = variable.Key;
    System.Object value = variable.Value;
}   
```


Note that as of v2.0, this class no longer uses Yarn.Value, to
enforce static typing of declared variables within the Yarn Program.




## Methods
|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.unity/inmemoryvariablestorage.clear.md)| Removes all variables from storage. |
|[DeserializeAllVariablesFromJSON(String)](/api/csharp/yarn.unity/inmemoryvariablestorage.deserializeallvariablesfromjson-system.string-.md)| Import a JSON string into variable storage, like when loading save game data. |
|[GetDebugList()](/api/csharp/yarn.unity/inmemoryvariablestorage.getdebuglist.md)||
|[LoadFromFile(String)](/api/csharp/yarn.unity/inmemoryvariablestorage.loadfromfile-system.string-.md)| Load JSON data from a file, then deserialize as variables. |
|[LoadFromPlayerPrefs()](/api/csharp/yarn.unity/inmemoryvariablestorage.loadfromplayerprefs.md)| Load JSON data from Unity's built-in PlayerPrefs with default playerPrefsKey, and deserialize as variables. |
|[LoadFromPlayerPrefs(String)](/api/csharp/yarn.unity/inmemoryvariablestorage.loadfromplayerprefs-system.string-.md)| Load JSON data from Unity's built-in PlayerPrefs with defined playerPrefsKey parameter, and deserialize as variables. |
|[SaveToFile(String)](/api/csharp/yarn.unity/inmemoryvariablestorage.savetofile-system.string-.md)| Serialize all variables to JSON, then write the data to a file. |
|[SaveToPlayerPrefs()](/api/csharp/yarn.unity/inmemoryvariablestorage.savetoplayerprefs.md)| Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs with default playerPrefsKey. |
|[SaveToPlayerPrefs(String)](/api/csharp/yarn.unity/inmemoryvariablestorage.savetoplayerprefs-system.string-.md)| Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs under playerPrefsKey parameter. |
|[SerializeAllVariablesToJSON(Boolean)](/api/csharp/yarn.unity/inmemoryvariablestorage.serializeallvariablestojson-system.boolean-.md)| Export variable storage to a JSON string, like when writing save game data. |
|[SetValue(String, Boolean)](/api/csharp/yarn.unity/inmemoryvariablestorage.setvalue-system.string,system.boolean-.md)||
|[SetValue(String, Single)](/api/csharp/yarn.unity/inmemoryvariablestorage.setvalue-system.string,system.single-.md)||
|[SetValue(String, String)](/api/csharp/yarn.unity/inmemoryvariablestorage.setvalue-system.string,system.string-.md)||
|[TryGetValue<T>(String, out T)](/api/csharp/yarn.unity/inmemoryvariablestorage.trygetvalue--1-system.string,--0@-.md)| Retrieves a <see cref="!:Value"></see> by name. |
## Fields
|Name|Description|
|:---|:---|
|[showDebug](/api/csharp/yarn.unity/inmemoryvariablestorage.showdebug.md)||
|[TypeMappings](/api/csharp/yarn.unity/inmemoryvariablestorage.typemappings.md)||
<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/InMemoryVariableStorage.cs#L54), line 54.
