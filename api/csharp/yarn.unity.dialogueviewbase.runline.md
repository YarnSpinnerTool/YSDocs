# RunLine(LocalizedLine,Action)

Method in [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a
line should be displayed to the user.


```csharp
public virtual void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Parameters

|Name|Description|
|:---|:---|
|dialogueLine|The content of the line that should be presented to the user.|
|onDialogueLineFinished|The method that should be called after the line has been finished.|

## Returns



