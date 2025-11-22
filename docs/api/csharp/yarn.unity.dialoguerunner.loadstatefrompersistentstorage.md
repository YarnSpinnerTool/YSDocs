# DialogueRunner.LoadStateFromPersistentStorage(string)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Loads all variables from the requested file in persistent storage
into the Dialogue Runner's variable storage.


```csharp
public bool LoadStateFromPersistentStorage(string saveFileName)
```

## Remarks

<p>
This method loads the file <code>saveFileName</code> from the
persistent data storage and attempts to read it as JSON. This is
then deserialised and loaded into the <a href="yarn.unity.dialoguerunner.variablestorage.md">VariableStorage</a>.
</p> <p>
The loaded information can be stored via the <a href="yarn.unity.dialoguerunner.savestatetopersistentstorage.md">SaveStateToPersistentStorage(string)</a> method.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` saveFileName|the name the save file should have on disc, including any file extension|

## Returns

<code>true</code>  if the variables were successfully
loaded from the player preferences;  <code>false</code> 
otherwise.

