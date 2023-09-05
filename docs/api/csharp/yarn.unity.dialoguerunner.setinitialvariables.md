# DialogueRunner.SetInitialVariables(bool)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Loads any initial variables declared in the program and loads that variable with its default declaration value into the variable storage.
Any variable that is already in the storage will be skipped, the assumption is that this means the value has been overridden at some point and shouldn't be otherwise touched.
Can force an override of the existing values with the default if that is desired.


```csharp
public void SetInitialVariables(bool overrideExistingValues = false)
```

## Parameters

|Name|Description|
|:---|:---|
|`bool` overrideExistingValues||

