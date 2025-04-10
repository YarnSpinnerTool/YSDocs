# RunOptionsAsync(DialogueOption\[],CancellationToken)

Method in [AsyncDialogueViewBase](yarn.unity.asyncdialogueviewbase.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.

```csharp
public abstract YarnTask<DialogueOption?> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken);
```

## Remarks

This method is called when the Dialogue Runner wants to show a collection of options that the user should choose from. Each option is represented by a [DialogueOption](yarn.unity.dialogueoption.md) object, which contains information about the option.

When this method is called, the Dialogue View should display appropriate user interface elements that let the user choose among the options.

This method should await until an option is selected, and then return the selected option. If this view doesn't handle options, or is otherwise unable to select an option, it should return `YarnAsync.NoOptionSelected`. The dialogue runner will wait for all dialogue views to return, so if a dialogue view doesn't or can't handle options, it's good practice to return as soon as possible.

If the `cancellationToken` becomes cancelled, this means that the dialogue runner no longer needs this dialogue view to make a selection, and this method should return as soon as possible; its return value will not be used.

{% hint style="info" %}
The default implementation of this method returns `YarnAsync.NoOptionSelected`.
{% endhint %}

## Parameters

| Name                                                                          | Description                                                                                                                                    |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions | The set of options that should be displayed to the user.                                                                                       |
| `System.Threading.CancellationToken` cancellationToken                        | A `System.Threading.CancellationToken` that becomes cancelled when the dialogue runner no longer needs this dialogue view to return an option. |

## Returns

A task that indicates which option was selected, or that this dialogue view did not select an option.

## See Also

* [AsyncDialogueViewBase.RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.asyncdialogueviewbase.runlineasync.md): Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.
* YarnAsync.NoOptionSelected
