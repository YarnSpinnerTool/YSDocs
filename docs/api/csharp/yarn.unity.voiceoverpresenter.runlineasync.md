# RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [VoiceOverPresenter](yarn.unity.voiceoverpresenter.md)

## Summary

Begins playing the associated audio for the specified line.

```csharp
public override async YarnTask RunLineAsync(LocalizedLine dialogueLine, LineCancellationToken lineCancellationToken)
```

## Remarks

{% hint style="warning" %}
This method is not intended to be called from\
your code. Instead, the [DialogueRunner](yarn.unity.dialoguerunner.md) class will call\
it at the appropriate time.
{% endhint %}

## Parameters

| Name                                                                                          | Description                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| line                                                                                          | The line to present.                                                                                                                                                                          |
| token                                                                                         | A [LineCancellationToken](yarn.unity.linecancellationtoken.md) that represents whether the dialogue presenter should hurry it its presentation of the line, or stop showing the current line. |
| [Yarn.Unity.LocalizedLine](yarn.unity.localizedline.md) dialogueLine                          |                                                                                                                                                                                               |
| [Yarn.Unity.LineCancellationToken](yarn.unity.linecancellationtoken.md) lineCancellationToken |                                                                                                                                                                                               |

## See Also

* [DialoguePresenterBase.RunLineAsync(LocalizedLine,LineCancellationToken)](yarn.unity.dialoguepresenterbase.runlineasync.md): Called by the [DialogueRunner](yarn.unity.dialoguerunner.md) to signal that a line should be displayed to the user.
