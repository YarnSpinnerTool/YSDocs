# SaveStateToPersistentStorage(string)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Saves all variables from variable storage into the persistent storage.

```csharp
public bool SaveStateToPersistentStorage(string saveFileName)
```

## Remarks

This method attempts to writes the contents of [VariableStorage](yarn.unity.dialoguerunner.variablestorage.md) as a JSON file and saves it to the persistent data storage under the file name `saveFileName`. The saved information can be loaded via the [LoadStateFromPersistentStorage(string)](yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md) method.

If `saveFileName` already exists, it will be overwritten, not appended.

## Parameters

| Name                  | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| `string` saveFileName | the name the save file should have on disc, including any file extension |

## Returns

`true` if the variables were successfully written into the player preferences; `false` otherwise.
