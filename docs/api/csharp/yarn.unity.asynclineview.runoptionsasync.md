# RunOptionsAsync(DialogueOption\[],CancellationToken)

Method in [AsyncLineView](yarn.unity.asynclineview.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.

```csharp
public override YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
```

## Remarks

This dialogue view does not handle any options.

## Parameters

| Name                                                                          | Description                                                                                                                                    |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions | The set of options that should be displayed to the user.                                                                                       |
| `System.Threading.CancellationToken` cancellationToken                        | A `System.Threading.CancellationToken` that becomes cancelled when the dialogue runner no longer needs this dialogue view to return an option. |

## Returns

A task that indicates which option was selected, or that this dialogue view did not select an option.
