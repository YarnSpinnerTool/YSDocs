# DialogueViewBase.RunLineAsync(LocalizedLine,LineCancellationToken)

Method in [DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line
should be displayed to the user.


```csharp
public override async YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
```

## Remarks

<p>
When this method is called, the Dialogue View should present the
line to the user. The content to present is contained within the
<code>line</code> parameter, which contains information about
the line in the user's current locale.
</p> <p>
{% hint style="tip" %}

It's up to the Dialogue View to decide what "presenting" the line
may mean; for example, showing on-screen text, playing voice-over
audio, or updating on-screen portraits to show a picture of the
speaking character.

{% endhint %}
</p> <p>
The <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will wait until the tasks from all
of its dialogue views have completed before continuing to the next
piece of content. If your dialogue view does not need to handle the
line, it should return immediately.
</p> <p>
{% hint style="info" %}
The value of the <code>line</code>
parameter is produced by the Dialogue Runner's <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>.

{% endhint %}
</p> <p>
{% hint style="info" %}

The default implementation of this method takes no action and
returns immediately.

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) line|The line to present.|
|[Yarn.Unity.LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md) token|A  <a href="yarn.unity.linecancellationtoken.md">LineCancellationToken</a>  that represents whether the dialogue view should hurry it its presentation of the line, or stop showing the current line.|

## Returns

A task that completes when the dialogue view has finished
showing the line to the user.

## See Also

* [AsyncDialogueViewBase.RunOptionsAsync\(DialogueOption\[\],CancellationToken\)](/docs/api/csharp/yarn.unity.asyncdialogueviewbase.runoptionsasync.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.
