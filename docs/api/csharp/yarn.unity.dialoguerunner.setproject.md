# DialogueRunner.SetProject(YarnProject)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Sets the dialogue runner's Yarn Project.


```csharp
public void SetProject(YarnProject project)
```

## Remarks


If the dialogue runner is currently running (that is,  <a href="yarn.unity.dialoguerunner.isdialoguerunning.md">IsDialogueRunning</a>  is  <code>true</code> ), an  <code>System.InvalidOperationException</code>  is thrown.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.YarnProject](/docs/api/csharp/yarn.unity.yarnproject.md) project|The new  <a href="yarn.unity.dialoguerunner.yarnproject.md">YarnProject</a>  to be used.|

