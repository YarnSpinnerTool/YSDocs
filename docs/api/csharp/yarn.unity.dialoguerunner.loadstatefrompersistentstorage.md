# LoadStateFromPersistentStorage(string)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Loads all variables from the requested file in persistent storage\
into the Dialogue Runner's variable storage.

```csharp
public bool LoadStateFromPersistentStorage(string saveFileName)
```

## Remarks

This method loads the file `saveFileName` from the\
persistent data storage and attempts to read it as JSON. This is\
then deserialised and loaded into the [VariableStorage](yarn.unity.dialoguerunner.variablestorage.md).

The loaded information can be stored via the [SaveStateToPersistentStorage(string)](yarn.unity.dialoguerunner.savestatetopersistentstorage.md) method.

## Parameters

| Name                  | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| `string` saveFileName | the name the save file should have on disc, including any file extension |

## Returns

`true` if the variables were successfully\
loaded from the player preferences; `false`\
otherwise.
