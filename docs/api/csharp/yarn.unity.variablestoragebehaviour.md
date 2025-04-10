# VariableStorageBehaviour

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A `UnityEngine.MonoBehaviour` that a [DialogueRunner](yarn.unity.dialoguerunner.md) uses to store and retrieve variables.

```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, Yarn.IVariableStorage
```

## Remarks

This abstract class inherits from `UnityEngine.MonoBehaviour` , which means that subclasses of this class can be attached to `UnityEngine.GameObject` s.

## Methods

| Name                                                                                                                            | Description                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| [Clear()](yarn.unity.variablestoragebehaviour.clear.md)                                                                         |                                                                                                                              |
| [Contains(string)](yarn.unity.variablestoragebehaviour.contains.md)                                                             | Returns a boolean value representing if a particular variable is inside the variable storage.                                |
| [GetAllVariables()](yarn.unity.variablestoragebehaviour.getallvariables.md)                                                     | Provides a unified interface for exporting all variables. Intended to be a point for custom saving, editors, etc.            |
| [GetVariableKind(string)](yarn.unity.variablestoragebehaviour.getvariablekind.md)                                               |                                                                                                                              |
| [SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)](yarn.unity.variablestoragebehaviour.setallvariables.md) | Provides a unified interface for loading many variables all at once. Will override anything already in the variable storage. |
| [SetValue(string,bool)](yarn.unity.variablestoragebehaviour.setvalue-3.md)                                                      |                                                                                                                              |
| [SetValue(string,float)](yarn.unity.variablestoragebehaviour.setvalue-2.md)                                                     |                                                                                                                              |
| [SetValue(string,string)](yarn.unity.variablestoragebehaviour.setvalue-1.md)                                                    |                                                                                                                              |
| [TryGetValue(string,T)](yarn.unity.variablestoragebehaviour.trygetvalue.md)                                                     |                                                                                                                              |

## Properties

| Name                                                                                    | Description |
| --------------------------------------------------------------------------------------- | ----------- |
| [Program](yarn.unity.variablestoragebehaviour.program.md)                               |             |
| [SmartVariableEvaluator](yarn.unity.variablestoragebehaviour.smartvariableevaluator.md) |             |
