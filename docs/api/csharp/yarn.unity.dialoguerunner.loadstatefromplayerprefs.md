# LoadStateFromPlayerPrefs(string)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

{% hint style="warning" %}
This method is obsolete and may be removed from a future version of Yarn Spinner: LoadStateFromPlayerPrefs is deprecated, please use LoadStateFromPersistentStorage instead.
{% endhint %}

## Summary

Loads all variables from the `UnityEngine.PlayerPrefs` object into the Dialogue Runner's variable storage.

```csharp
public bool LoadStateFromPlayerPrefs(string SaveKey = "YarnBasicSave")
```

## Remarks

This method loads a string containing JSON from the `UnityEngine.PlayerPrefs` object under the key `SaveKey`, deserializes that JSON, and then uses the resulting object to set all variables in [VariableStorage](yarn.unity.dialoguerunner.variablestorage.md).

The loaded information can be stored via the [SaveStateToPlayerPrefs(string)](yarn.unity.dialoguerunner.savestatetoplayerprefs.md) method.

## Parameters

| Name             | Description                                |
| ---------------- | ------------------------------------------ |
| `string` SaveKey | The key to use when storing the variables. |

## Returns

`true` if the variables were successfully loaded from the player preferences; `false` otherwise.

## See Also

* [VariableStorageBehaviour.SetAllVariables(FloatDictionary,StringDictionary,BoolDictionary,bool)](yarn.unity.variablestoragebehaviour.setallvariables.md): Provides a unified interface for loading many variables all at once. Will override anything already in the variable storage.
