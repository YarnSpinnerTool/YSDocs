# VariableStorageBehaviour.SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)

Method in [VariableStorageBehaviour](/docs/api/csharp/yarn.unity.variablestoragebehaviour.md)

## Summary


Provides a unified interface for loading many variables all at once.
Will override anything already in the variable storage.


```csharp
public abstract void SetAllVariables(FloatDictionary floats, StringDictionary strings, BoolDictionary bools, bool clear = true);
```

## Parameters

|Name|Description|
|:---|:---|
|`bool` clear|Should the load also wipe the storage. Defaults to true so all existing variables will be cleared.|
|`Dictionary<string, float>` floats||
|`Dictionary<string, string>` strings||
|`Dictionary<string, bool>` bools||

