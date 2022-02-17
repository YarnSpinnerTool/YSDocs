# VoiceOverView.DismissLine(Action)

Method in [VoiceOverView](/api/csharp/yarn.unity.voiceoverview.md)

## Summary


Ends any existing playback, and reports that the line has finished
dismissing.


```csharp
public override void DismissLine(Action onDismissalComplete)
```

## Remarks

<p>
{% hint style="warning" %}
This method is not intended to be called from
your code. Instead, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> class will call
it at the appropriate time.
{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|`Action` onDismissalComplete|The method that should be called when the view has finished dismissing the line.|

## See Also

* [DialogueViewBase.DismissLine\(Action\)](/api/csharp/yarn.unity.dialogueviewbase.dismissline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.

