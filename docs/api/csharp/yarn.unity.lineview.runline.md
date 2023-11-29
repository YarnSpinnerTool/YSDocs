# LineView.RunLine(LocalizedLine,Action)

Method in [LineView](/docs/api/csharp/yarn.unity.lineview.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line
should be displayed to the user.


```csharp
public override void RunLine(LocalizedLine dialogueLine, Action onDialogueLineFinished)
```

## Remarks

<p>
When this method is called, the Dialogue View should present the
line to the user. The content to present is contained within the
<code>dialogueLine</code> parameter, which contains
information about the line in the user's current locale.
</p> <p>
{% hint style="info" %}
The value of the <code>dialogueLine</code>
parameter is produced by the Dialogue Runner's <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>.

{% endhint %}
</p> <p>
It's up to the Dialogue View to decide what "presenting" the line
may mean; for example, showing on-screen text, or playing voice-over
audio.
</p> <p>When the line has finished being presented, this method calls
the <code>onDialogueLineFinished</code> method, which signals
to the Dialogue Runner that this Dialogue View has finished
presenting the line. When all Dialogue Views have finished
presenting the line, the Dialogue Runner calls <a href="yarn.unity.dialogueviewbase.dismissline.md">DismissLine(Action)</a> to signal that the views should get rid
of the line.</p> <p>
If you want to create a Dialogue View that waits for user input
before continuing, either wait for that input before calling
<code>onDialogueLineFinished</code>, or don't call it at all
and instead call <a href="yarn.unity.dialogueviewbase.requestinterrupt.md">requestInterrupt</a> to tell the Dialogue
Runner to interrupt the line.
</p> <p>
{% hint style="danger" %}

The <code>onDialogueLineFinished</code> method should only be
called when <a href="yarn.unity.dialogueviewbase.runline.md">RunLine(LocalizedLine,Action)</a> finishes its presentation
normally. If <a href="yarn.unity.dialogueviewbase.interruptline.md">InterruptLine(LocalizedLine,Action)</a> has been called, you must
call the completion handler that it receives, and not the completion
handler that <a href="yarn.unity.dialogueviewbase.runline.md">RunLine(LocalizedLine,Action)</a> has received.

{% endhint %}
</p> <p>
{% hint style="note" %}

The default implementation of this method immediately calls the
<code>onDialogueLineFinished</code> method (that is, it
reports that it has finished presenting the line the moment that it
receives it), and otherwise does nothing.

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) dialogueLine|The content of the line that should be presented to the user.|
|`System.Action` onDialogueLineFinished|The method that should be called after the line has finished being presented.|

## See Also

* [DialogueViewBase.InterruptLine\(LocalizedLine,Action\)](/docs/api/csharp/yarn.unity.dialogueviewbase.interruptline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible.
* [DialogueViewBase.DismissLine\(Action\)](/docs/api/csharp/yarn.unity.dialogueviewbase.dismissline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.
* [DialogueViewBase.RunOptions\(DialogueOption\[\],Action\<int\>\)](/docs/api/csharp/yarn.unity.dialogueviewbase.runoptions.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a set of options should be displayed to the user.

