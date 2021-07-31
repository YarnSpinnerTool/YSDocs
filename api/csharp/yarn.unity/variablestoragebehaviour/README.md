# VariableStorageBehaviour

A  that a [`DialogueRunner`](../dialoguerunner/) uses to store and retrieve variables.

```csharp
public abstract class VariableStorageBehaviour : MonoBehaviour, IVariableStorage
```

## Remarks

This abstract class inherits from , which means that subclasses of this class can be attached to s.

## Methods

| Name | Description |
| :--- | :--- |
| [`Clear()`](variablestoragebehaviour.clear.md) |  |
| [`SetValue(String, Boolean)`](variablestoragebehaviour.setvalue-system.string-system.boolean.md) |  |
| [`SetValue(String, Single)`](variablestoragebehaviour.setvalue-system.string-system.single.md) |  |
| [`SetValue(String, String)`](variablestoragebehaviour.setvalue-system.string-system.string.md) |  |
| [`TryGetValue<T>(String, out T)`](variablestoragebehaviour.trygetvalue-1-system.string-0.md) |  |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1431), line 1431.

