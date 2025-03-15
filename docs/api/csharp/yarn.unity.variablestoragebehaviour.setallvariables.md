# SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)

Method in [VariableStorageBehaviour](yarn.unity.variablestoragebehaviour.md)

## Summary

Provides a unified interface for loading many variables all at once. Will override anything already in the variable storage.

```csharp
public abstract void SetAllVariables(FloatDictionary floats, StringDictionary strings, BoolDictionary bools, bool clear = true);
```

## Parameters

| Name                                                            | Description                                                                                        |
| --------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `bool` clear                                                    | Should the load also wipe the storage. Defaults to true so all existing variables will be cleared. |
| `System.Collections.Generic.Dictionary<string, float>` floats   |                                                                                                    |
| `System.Collections.Generic.Dictionary<string, string>` strings |                                                                                                    |
| `System.Collections.Generic.Dictionary<string, bool>` bools     |                                                                                                    |
