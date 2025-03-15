# InMemoryVariableStorage

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`VariableStorageBehaviour`](yarn.unity.variablestoragebehaviour.md)

## Summary

A simple implementation of VariableStorageBehaviour.

```csharp
public class InMemoryVariableStorage : VariableStorageBehaviour, IEnumerable<KeyValuePair<string, object>>
```

## Remarks

This class stores variables in memory, and is erased when the game exits.

This class also has basic serialization and save/load example functions.

You can also enumerate over the variables by using a `foreach` loop:

```
// 'storage' is an InMemoryVariableStorage
foreach (var variable in storage) {
string name = variable.Key;
System.Object value = variable.Value;
}
```

Note that as of v2.0, this class no longer uses Yarn.Value, to enforce static typing of declared variables within the Yarn Program.

## Fields

| Name                                                         | Description |
| ------------------------------------------------------------ | ----------- |
| [showDebug](yarn.unity.inmemoryvariablestorage.showdebug.md) |             |

## Methods

| Name                                                                                                                                                            | Description                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [Clear()](yarn.unity.inmemoryvariablestorage.clear.md)                                                                                                          | Removes all variables from storage.                                                            |
| [Contains(string)](yarn.unity.inmemoryvariablestorage.contains.md)                                                                                              | returns a boolean value representing if the particular variable is inside the variable storage |
| [GetAllVariables()](yarn.unity.inmemoryvariablestorage.getallvariables.md)                                                                                      |                                                                                                |
| [GetDebugList()](yarn.unity.inmemoryvariablestorage.getdebuglist.md)                                                                                            |                                                                                                |
| [SetAllVariables(Dictionary\<string, float>,Dictionary\<string, string>,Dictionary\<string, bool>,bool)](yarn.unity.inmemoryvariablestorage.setallvariables.md) |                                                                                                |
| [SetValue(string,bool)](yarn.unity.inmemoryvariablestorage.setvalue-3.md)                                                                                       |                                                                                                |
| [SetValue(string,float)](yarn.unity.inmemoryvariablestorage.setvalue-2.md)                                                                                      |                                                                                                |
| [SetValue(string,string)](yarn.unity.inmemoryvariablestorage.setvalue-1.md)                                                                                     |                                                                                                |
| [TryGetValue(string,T)](yarn.unity.inmemoryvariablestorage.trygetvalue.md)                                                                                      | Retrieves a `Yarn.Value` by name.                                                              |
