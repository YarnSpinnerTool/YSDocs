# VariableStorageBehaviour

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `MonoBehaviour`

## Summary


A  <code>MonoBehaviour</code>  that a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> 
uses to store and retrieve variables.


```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, Yarn.IVariableStorage
```

## Remarks


This abstract class inherits from  <code>MonoBehaviour</code> ,
which means that subclasses of this class can be attached to  <code>GameObject</code> s.


## Methods

|Name|Description|
|:---|:---|
|[Clear()](/api/csharp/yarn.unity.variablestoragebehaviour.clear.md)||
|[Contains(string)](/api/csharp/yarn.unity.variablestoragebehaviour.contains.md)|Returns a boolean value representing if a particular variable is inside the variable storage.|
|[SetValue(string,bool)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-3.md)||
|[SetValue(string,float)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-2.md)||
|[SetValue(string,string)](/api/csharp/yarn.unity.variablestoragebehaviour.setvalue-1.md)||
|[TryGetValue(string,T)](/api/csharp/yarn.unity.variablestoragebehaviour.trygetvalue.md)||
