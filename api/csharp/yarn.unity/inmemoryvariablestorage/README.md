# InMemoryVariableStorage

A simple implementation of VariableStorageBehaviour.

```csharp
public class InMemoryVariableStorage : VariableStorageBehaviour, IVariableStorage, IEnumerable<KeyValuePair<string, object>>
```

## Remarks

As of v2.0, this class has basic serialization and save/load example functions. You can also enumerate over the variables by using a `foreach` loop:

```csharp
// 'storage' is an InMemoryVariableStorage    
foreach (var variable in storage) {
    string name = variable.Key;
    System.Object value = variable.Value;
}
```

Note that as of v2.0, this class no longer uses Yarn.Value, to enforce static typing of declared variables within the Yarn Program.

## Methods

| Name | Description |
| :--- | :--- |
| [`Clear()`](inmemoryvariablestorage.clear.md) | Removes all variables from storage. |
| [`DeserializeAllVariablesFromJSON(String)`](inmemoryvariablestorage.deserializeallvariablesfromjson-system.string.md) | Import a JSON string into variable storage, like when loading save game data. |
| [`GetDebugList()`](inmemoryvariablestorage.getdebuglist.md) |  |
| [`LoadFromFile(String)`](inmemoryvariablestorage.loadfromfile-system.string.md) | Load JSON data from a file, then deserialize as variables. |
| [`LoadFromPlayerPrefs()`](inmemoryvariablestorage.loadfromplayerprefs.md) | Load JSON data from Unity's built-in PlayerPrefs with default playerPrefsKey, and deserialize as variables. |
| [`LoadFromPlayerPrefs(String)`](inmemoryvariablestorage.loadfromplayerprefs-system.string.md) | Load JSON data from Unity's built-in PlayerPrefs with defined playerPrefsKey parameter, and deserialize as variables. |
| [`SaveToFile(String)`](inmemoryvariablestorage.savetofile-system.string.md) | Serialize all variables to JSON, then write the data to a file. |
| [`SaveToPlayerPrefs()`](inmemoryvariablestorage.savetoplayerprefs.md) | Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs with default playerPrefsKey. |
| [`SaveToPlayerPrefs(String)`](inmemoryvariablestorage.savetoplayerprefs-system.string.md) | Serialize all variables to JSON, then save data to Unity's built-in PlayerPrefs under playerPrefsKey parameter. |
| [`SerializeAllVariablesToJSON(Boolean)`](inmemoryvariablestorage.serializeallvariablestojson-system.boolean.md) | Export variable storage to a JSON string, like when writing save game data. |
| [`SetValue(String, Boolean)`](inmemoryvariablestorage.setvalue-system.string-system.boolean.md) |  |
| [`SetValue(String, Single)`](inmemoryvariablestorage.setvalue-system.string-system.single.md) |  |
| [`SetValue(String, String)`](inmemoryvariablestorage.setvalue-system.string-system.string.md) |  |
| [`TryGetValue<T>(String, out T)`](inmemoryvariablestorage.trygetvalue-1-system.string-0.md) | Retrieves a  by name. |

## Fields

| Name | Description |
| :--- | :--- |
| [`showDebug`](inmemoryvariablestorage.showdebug.md) |  |
| [`TypeMappings`](inmemoryvariablestorage.typemappings.md) |  |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/InMemoryVariableStorage.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/InMemoryVariableStorage.cs#L54), line 54.

