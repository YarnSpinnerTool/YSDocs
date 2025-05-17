# DialogueRunner.SetProject(YarnProject)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Sets the dialogue runner's Yarn Project.


```csharp
public void SetProject(YarnProject project)
```

## Remarks


If the dialogue runner is currently running (that is,  [IsDialogueRunning](yarn.unity.dialoguerunner.isdialoguerunning.md)  is  `true` ), an  `System.InvalidOperationException`  is thrown.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.YarnProject](/docs/api/csharp/yarn.unity.yarnproject.md) project|The new  [YarnProject](yarn.unity.dialoguerunner.yarnproject.md)  to be used.|

