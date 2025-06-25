# DialogueTask

Property in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Gets a [YarnTask](yarn.unity.yarntask-1.md) that completes when the dialogue\
runner finishes its dialogue.

```csharp
public YarnTask DialogueTask { get; }
```

## Remarks

If the dialogue is not currently running when this property is\
accessed, the property returns a task that is already complete.
