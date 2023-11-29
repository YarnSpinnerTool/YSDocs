# DialogueRunner.SaveStateToPersistentStorage(string)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Saves all variables from variable storage into the persistent
storage.


```csharp
public bool SaveStateToPersistentStorage(string saveFileName)
```

## Remarks

<p>
This method attempts to writes the contents of <a href="yarn.unity.dialoguerunner.variablestorage.md">VariableStorage</a> as a JSON file and saves it to the
persistent data storage under the file name <code>saveFileName</code>. The saved information can be loaded via the
<a href="yarn.unity.dialoguerunner.loadstatefrompersistentstorage.md">LoadStateFromPersistentStorage(string)</a> method.
</p> <p>
If <code>saveFileName</code> already exists, it will be
overwritten, not appended.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` saveFileName|the name the save file should have on disc, including any file extension|

## Returns

<code>true</code>  if the variables were successfully
written into the player preferences;  <code>false</code> 
otherwise.

