# RunOptionsAsync(DialogueOption\[],CancellationToken)

Method in [OptionsPresenter](yarn.unity.optionspresenter.md)

## Summary

Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) to display a collection of\
options to the user.

```csharp
public override async YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Parameters

| Name                                                                          | Description                                                                                                                                         |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions | The set of options that should be displayed to the user.                                                                                            |
| `CancellationToken` cancellationToken                                         | A `System.Threading.CancellationToken` that becomes cancelled when the dialogue runner no longer needs this dialogue presenter to return an option. |

## Returns

A task that indicates which option was selected, or that this dialogue presenter did not select an option.
