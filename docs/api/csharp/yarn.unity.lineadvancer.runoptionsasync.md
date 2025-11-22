# LineAdvancer.RunOptionsAsync(DialogueOption[],LineCancellationToken)

Method in [LineAdvancer](/docs/api/csharp/yarn.unity.lineadvancer.md)

## Summary


Called by a dialogue presenter to signal that options are running.


```csharp
public override YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, LineCancellationToken cancellationToken)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.DialogueOption\[\]](/docs/api/csharp/yarn.unity.dialogueoption.md) dialogueOptions||
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) cancellationToken||

## Returns

A completed task indicating that no option was selected by
this view.

