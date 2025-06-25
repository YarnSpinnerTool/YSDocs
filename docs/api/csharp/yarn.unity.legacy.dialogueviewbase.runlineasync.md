# RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [DialogueViewBase](yarn.unity.legacy.dialogueviewbase.md)

## Summary

Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line\
should be displayed to the user.

```csharp
public override async YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

When this method is called, the Dialogue Presenter should present the\
line to the user. The content to present is contained within the`line` parameter, which contains information about\
the line in the user's current locale.

{% hint style="info" %}
It's up to the Dialogue Presenter to decide what "presenting" the line\
may mean; for example, showing on-screen text, playing voice-over\
audio, or updating on-screen portraits to show a picture of the\
speaking character.
{% endhint %}

The [DialogueRunner](yarn.unity.dialoguerunner.md) will wait until the tasks from all\
of its dialogue presenters have completed before continuing to the next\
piece of content. If your dialogue presenter does not need to handle the\
line, it should return immediately.

{% hint style="info" %}
The value of the `line`\
parameter is produced by the Dialogue Runner's [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md).
{% endhint %}

{% hint style="info" %}
The default implementation of this method takes no action and\
returns immediately.
{% endhint %}

## Parameters

| Name                                                                          | Description                                                                                                                                                                                   |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) line                  | The line to present.                                                                                                                                                                          |
| [Yarn.Unity.LineCancellationToken](yarn.unity.linecancellationtoken.md) token | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue presenter should hurry it its presentation of the line, or stop showing the current line. |

## Returns

A task that completes when the dialogue presenter has finished\
showing the line to the user.

## See Also

* [DialoguePresenterBase.RunOptionsAsync(DialogueOption\[\],CancellationToken)](yarn.unity.dialoguepresenterbase.runoptionsasync.md): Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a set of options should be displayed to the user.
