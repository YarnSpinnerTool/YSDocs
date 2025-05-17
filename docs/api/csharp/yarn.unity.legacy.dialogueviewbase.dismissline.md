# DialogueViewBase.DismissLine(Action)

Method in [DialogueViewBase](/docs/api/csharp/yarn.unity.legacy.dialogueviewbase.md)

## Summary


Called by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to signal that the view
should dismiss its current line from display, and clean up.


```csharp
public virtual void DismissLine(Action onDismissalComplete)
```

## Remarks

<p>
This method is called when all Dialogue Views attached to a Dialogue
Runner report that they have finished presenting this line. When
this occurs, the Dialogue Runner calls <a href="yarn.unity.legacy.dialogueviewbase.dismissline.md">DismissLine(Action)</a> on
all Dialogue Views to tell them to clear their current line from
display.</p> <p>Depending on how the Dialogue View presents lines,
"dismissing" a line may mean different things. For example, a
Dialogue View that presents on-screen text might fade the text away,
or a Dialogue View that presents voice-over dialogue may not need to
do anything at all (because audio finished playing when the line
finished presenting.)
</p> <p>
{% hint style="hint" %}

Dismissing the line can take time, but should ideally be as fast as
possible, because the user will be waiting for the next piece of
content to appear. 
{% endhint %}
</p> <p>
When the line has finished dismissing, this method calls
onDismissalComplete to indicate that the dismissal is complete. When
all Dialogue Views on a Dialogue Runner have finished dismissing,
the Dialogue Runner moves on to the next piece of content.
</p> <p>
{% hint style="note" %}

The default implementation of this method immediately calls the
<code>onDismissalComplete</code> method (that is, it reports
that it has finished dismissing the line the moment that it receives
it), and otherwise does nothing.

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|`Action` onDismissalComplete|The method that should be called when the view has finished dismissing the line.|

