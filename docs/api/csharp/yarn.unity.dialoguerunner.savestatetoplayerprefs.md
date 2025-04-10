# SaveStateToPlayerPrefs(string)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

{% hint style="warning" %}
This method is obsolete and may be removed from a future version of Yarn Spinner: SaveStateToPlayerPrefs is deprecated, please use SaveStateToPersistentStorage instead.
{% endhint %}

## Summary

Saves all variables in the Dialogue Runner's variable storage into the `UnityEngine.PlayerPrefs` object.

```csharp
public void SaveStateToPlayerPrefs(string SaveKey = "YarnBasicSave")
```

## Remarks

This method serializes all variables in [VariableStorage](yarn.unity.dialoguerunner.variablestorage.md) into a string containing JSON, and then stores that string in the `UnityEngine.PlayerPrefs` object under the key `SaveKey`.

The stored information can be restored via the [LoadStateFromPlayerPrefs(string)](yarn.unity.dialoguerunner.loadstatefromplayerprefs.md) method.

## Parameters

| Name             | Description                                |
| ---------------- | ------------------------------------------ |
| `string` SaveKey | The key to use when storing the variables. |

## See Also

* [VariableStorageBehaviour.GetAllVariables()](yarn.unity.variablestoragebehaviour.getallvariables.md): Provides a unified interface for exporting all variables. Intended to be a point for custom saving, editors, etc.
