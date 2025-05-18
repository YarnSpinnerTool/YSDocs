# LineAdvancer.RunOptionsAsync(DialogueOption[],CancellationToken)

Method in [LineAdvancer](/docs/api/csharp/yarn.unity.lineadvancer.md)

## Summary


Called by a dialogue presenter to signal that options are running.


```csharp
public override YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.DialogueOption\[\]](/docs/api/csharp/yarn.unity.dialogueoption.md) dialogueOptions|The set of options that should be displayed to the user.|
|`CancellationToken` cancellationToken|A  <code>System.Threading.CancellationToken</code>  that becomes cancelled when the dialogue runner no longer needs this dialogue presenter to return an option.|

## Returns

A completed task indicating that no option was selected by
this view.

