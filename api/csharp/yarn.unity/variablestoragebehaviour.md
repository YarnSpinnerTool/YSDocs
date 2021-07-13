# VariableStorageBehaviour Class

A <see cref="!:MonoBehaviour"></see> that a [`DialogueRunner`](/api/csharp/yarn.unity/dialoguerunner.md)
uses to store and retrieve variables.


```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, IVariableStorage
```
## Remarks

This abstract class inherits from <see cref="!:MonoBehaviour"></see>,
which means that subclasses of this class can be attached to <see cref="!:GameObject"></see>s.




## Methods
|Name|Description|
|:---|:---|
|[`Clear()`](/api/csharp/yarn.unity/variablestoragebehaviour.clear.md)||
|[`SetValue(String, Boolean)`](/api/csharp/yarn.unity/variablestoragebehaviour.setvalue-system.string,system.boolean-.md)||
|[`SetValue(String, Single)`](/api/csharp/yarn.unity/variablestoragebehaviour.setvalue-system.string,system.single-.md)||
|[`SetValue(String, String)`](/api/csharp/yarn.unity/variablestoragebehaviour.setvalue-system.string,system.string-.md)||
|[`TryGetValue<T>(String, out T)`](/api/csharp/yarn.unity/variablestoragebehaviour.trygetvalue--1-system.string,--0@-.md)||
<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1431), line 1431.
