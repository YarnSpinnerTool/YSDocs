# VariableStorageBehaviour

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


A  <code>UnityEngine.MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> 
uses to store and retrieve variables.


```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, Yarn.IVariableStorage
```

## Remarks


This abstract class inherits from  <code>UnityEngine.MonoBehaviour</code> ,
which means that subclasses of this class can be attached to  <code>UnityEngine.GameObject</code> s.


## Methods

|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.unity.variablestoragebehaviour.clear.md)||
|[Contains(string)](/api/csharp/yarn.unity.variablestoragebehaviour.contains.md)|Returns a boolean value representing if a particular variable is inside the variable storage.|
|[GetAllVariables()](/api/csharp/yarn.unity.variablestoragebehaviour.getallvariables.md)|Provides a unified interface for exporting all variables. Intended to be a point for custom saving, editors, etc.|
|[SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)](/api/csharp/yarn.unity.variablestoragebehaviour.setallvariables.md)|Provides a unified interface for loading many variables all at once. Will override anything already in the variable storage.|
|[SetValue(string,bool)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-3.md)||
|[SetValue(string,float)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-2.md)||
|[SetValue(string,string)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-1.md)||
|[TryGetValue(string,T)](/api/csharp/yarn.unity.variablestoragebehaviour.trygetvalue.md)||

