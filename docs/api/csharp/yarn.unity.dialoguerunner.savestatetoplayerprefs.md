# DialogueRunner.SaveStateToPlayerPrefs(string)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Saves all variables in the Dialogue Runner's variable storage into
the  <code>UnityEngine.PlayerPrefs</code>  object.


```csharp
public void SaveStateToPlayerPrefs(string SaveKey = "YarnBasicSave")
```

## Remarks

<p>
This method serializes all variables in <a href="yarn.unity.dialoguerunner.variablestorage.md">VariableStorage</a> into a string containing JSON, and then
stores that string in the <code>UnityEngine.PlayerPrefs</code> object under the
key <code>SaveKey</code>.
</p> <p>
The stored information can be restored via the <a href="yarn.unity.dialoguerunner.loadstatefromplayerprefs.md">LoadStateFromPlayerPrefs(string)</a> method.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` SaveKey|The key to use when storing the variables.|

## See Also

* [VariableStorageBehaviour.GetAllVariables\(\)](/docs/api/csharp/yarn.unity.variablestoragebehaviour.getallvariables.md): Provides a unified interface for exporting all variables. Intended to be a point for custom saving, editors, etc.

