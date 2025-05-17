# OptionsPresenter.RunOptionsAsync(DialogueOption[],CancellationToken)

Method in [OptionsPresenter](/docs/api/csharp/yarn.unity.optionspresenter.md)

## Summary


Called by a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to display a collection of
options to the user. 


```csharp
public override async YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.DialogueOption\[\]](/docs/api/csharp/yarn.unity.dialogueoption.md) dialogueOptions|The set of options that should be displayed to the user.|
|`CancellationToken` cancellationToken|A  `System.Threading.CancellationToken`  that becomes cancelled when the dialogue runner no longer needs this dialogue view to return an option.|

## Returns

A task that indicates which option was selected, or that this dialogue view did not select an option.

