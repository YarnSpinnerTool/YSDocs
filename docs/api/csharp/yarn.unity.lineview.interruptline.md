# LineView.InterruptLine(LocalizedLine,Action)

Method in [LineView](/docs/api/csharp/yarn.unity.lineview.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line has
been interrupted, and that the Dialogue View should finish
presenting its line as quickly as possible.


```csharp
public override void InterruptLine(LocalizedLine dialogueLine, Action onInterruptLineFinished)
```

## Remarks

<p>
This method is called when Dialogue Runner wants to interrupt the
presentation of the current line, in order to proceed to the next
piece of content.
</p> <p>
When this method is called, the Dialogue View must finish presenting
their line as quickly as it can. Depending on how this Dialogue View
presents lines, this can mean different things: for example, a view
that plays voice-over audio might stop playback immediately, or fade
out playback over a short period of time; a view that displays text
a letter at a time might display all of the text at once.
</p> <p>
The process of finishing the presentation can take time to complete,
but should happen as quickly as possible, because this method is
generally called when the user wants to skip the current line.
</p> <p>
When the line has finished presenting, the <code>onDialogueLineFinished</code> method must be called, which
indicates to the Dialogue Runner that this line is ready to be
dismissed.
</p> <p>
{% hint style="danger" %}

When <a href="yarn.unity.dialogueviewbase.interruptline.md">InterruptLine(LocalizedLine,Action)</a> is called, you must not call the
completion handler that <a href="yarn.unity.dialogueviewbase.runline.md">RunLine(LocalizedLine,Action)</a> has previously
received - this completion handler is no longer valid. Call this method's <code>onDialogueLineFinished</code> instead.

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
|[Yarn.Unity.LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md) dialogueLine|The current line that is being presented.|
| onDialogueLineFinished|The method that should be called after the line has finished being presented.|
|`Action` onInterruptLineFinished||

## See Also

* [DialogueViewBase.RunLine\(LocalizedLine,Action\)](/docs/api/csharp/yarn.unity.dialogueviewbase.runline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that a line should be displayed to the user.
* [DialogueViewBase.DismissLine\(Action\)](/docs/api/csharp/yarn.unity.dialogueviewbase.dismissline.md): Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view should dismiss its current line from display, and clean up.

