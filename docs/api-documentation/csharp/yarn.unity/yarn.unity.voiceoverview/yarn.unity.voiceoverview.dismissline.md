# DismissLine(Action)

Method in [VoiceOverView](./)

## Summary

Ends any existing playback, and reports that the line has finished dismissing.

```csharp
public override void DismissLine(Action onDismissalComplete)
```

## Remarks

{% hint style="warning" %}
This method is not intended to be called from your code. Instead, the [DialogueRunner](../yarn.unity.dialoguerunner/) class will call it at the appropriate time.
{% endhint %}

## Parameters

| Name                                | Description                                                                      |
| ----------------------------------- | -------------------------------------------------------------------------------- |
| `System.Action` onDismissalComplete | The method that should be called when the view has finished dismissing the line. |

## See Also

* [DialogueViewBase.DismissLine(Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.dismissline.md): Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.
