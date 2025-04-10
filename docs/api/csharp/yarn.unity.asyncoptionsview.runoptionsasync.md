# RunOptionsAsync(DialogueOption\[],CancellationToken)

Method in [AsyncOptionsView](yarn.unity.asyncoptionsview.md)

## Summary

Called by a [DialogueRunner](yarn.unity.dialoguerunner.md) to display a collection of options to the user.

```csharp
public override async YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Parameters

| Name                                                                          | Description                                                                                                                                    |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions | The set of options that should be displayed to the user.                                                                                       |
| `System.Threading.CancellationToken` cancellationToken                        | A `System.Threading.CancellationToken` that becomes cancelled when the dialogue runner no longer needs this dialogue view to return an option. |

## Returns

A task that indicates which option was selected, or that this dialogue view did not select an option.
