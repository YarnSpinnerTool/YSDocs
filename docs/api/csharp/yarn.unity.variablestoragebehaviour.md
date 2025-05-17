# VariableStorageBehaviour

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


A  `UnityEngine.MonoBehaviour`  that a  [DialogueRunner](yarn.unity.dialoguerunner.md)  uses
to store and retrieve variables.


```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, Yarn.IVariableStorage
```

## Remarks


This abstract class inherits from  `UnityEngine.MonoBehaviour` , which
means that subclasses of this class can be attached to  `UnityEngine.GameObject` s.


## Methods

|Name|Description|
|:---|:---|
|[AddChangeListener(string,Action<T>)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.addchangelistener.md)|Registers a delegate that will be called when the variable  `variableName`  is modified.|
|[Clear()](/docs/api/csharp/yarn.unity.variablestoragebehaviour.clear.md)||
|[Contains(string)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.contains.md)|Returns a boolean value representing if a particular variable is inside the variable storage.|
|[GetAllVariables()](/docs/api/csharp/yarn.unity.variablestoragebehaviour.getallvariables.md)|Provides a unified interface for exporting all variables. Intended to be a point for custom saving, editors, etc.|
|[GetVariableKind(string)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.getvariablekind.md)||
|[SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.setallvariables.md)|Provides a unified interface for loading many variables all at once. Will override anything already in the variable storage.|
|[SetValue(string,bool)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-3.md)||
|[SetValue(string,float)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-2.md)||
|[SetValue(string,string)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-1.md)||
|[TryGetValue(string,T?)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.trygetvalue.md)||

## Properties

|Name|Description|
|:---|:---|
|[Program](/docs/api/csharp/yarn.unity.variablestoragebehaviour.program.md)||
|[SmartVariableEvaluator](/docs/api/csharp/yarn.unity.variablestoragebehaviour.smartvariableevaluator.md)||

