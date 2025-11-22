# RunOptions(DialogueOption\[],Action\<int>)

Method in [DialogueViewBase](yarn.unity.legacy.dialogueviewbase.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of\
options should be displayed to the user.

```csharp
public virtual void RunOptions(DialogueOption[] dialogueOptions, Action<int> onOptionSelected)
```

## Remarks

This method is called when the Dialogue Runner wants to show a\
collection of options that the user should choose from. Each option\
is represented by a [DialogueOption](yarn.unity.dialogueoption.md) object, which\
contains information about the option.

When this method is called, the Dialogue View should display\
appropriate user interface elements that let the user choose among\
the options.

After this method is called, the [DialogueRunner](yarn.unity.dialoguerunner.md)\
will wait until the `onOptionSelected` method is\
called.

After calling the `onOptionSelected` method, the\
Dialogue View should dismiss whatever options UI it presented. The\
Dialogue Runner will immediately deliver the next piece of content.

{% hint style="warning" %}
When the Dialogue Runner delivers Options to\
its Dialogue Views, it expects precisely one of its views to call\
the `onOptionSelected` method.

* If your scene includes no dialogue views that override [RunOptions(DialogueOption\[\],Action\<int>)](yarn.unity.legacy.dialogueviewbase.runoptions.md), the Dialogue Runner will never be told which\
  option the user selected, and will therefore wait forever.
* If your scene includes multiple dialogue views that override[RunOptions(DialogueOption\[\],Action\<int>)](yarn.unity.legacy.dialogueviewbase.runoptions.md), they will all receive a call each time the\
  dialogue system presents options to the player. You must ensure that\
  only one of them calls the `onOptionSelected`\
  method.
{% endhint %}

{% hint style="info" %}
The default implementation of this method does nothing, and does not\
call the `onOptionSelected` method (that is, it\
ignores any Options it receives.)
{% endhint %}

## Parameters

| Name                                                                          | Description                                                        |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| [Yarn.Unity.DialogueOption\[\]](yarn.unity.dialogueoption.md) dialogueOptions | The set of options that should be displayed to the user.           |
| `Action<int>` onOptionSelected                                                | A method that should be called when the user has made a selection. |
