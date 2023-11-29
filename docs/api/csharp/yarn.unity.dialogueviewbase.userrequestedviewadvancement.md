# DialogueViewBase.UserRequestedViewAdvancement()

Method in [DialogueViewBase](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Called by  <a href="yarn.unity.dialogueadvanceinput.md">DialogueAdvanceInput</a>  to signal that the user
has requested that the dialogue advance.


```csharp
public virtual void UserRequestedViewAdvancement()
```

## Remarks

<p>
When this method is called, the Dialogue View should advance the
dialogue. Advancing the dialogue can mean different things,
depending on the nature of the dialogue view, and its current state.
</p> <p>
In many situations, if the Dialogue View hasn't yet finished
presenting its line (that is, the <a href="yarn.unity.dialogueviewbase.runline.md">RunLine(LocalizedLine,Action)</a> method has been called, but it hasn't yet called its
completion handler), it's sufficient to call the <a href="yarn.unity.dialogueviewbase.requestinterrupt.md">requestInterrupt</a> method, which tells the Dialogue Runner to
interrupt the current line.
</p> <p>
'Advancing' the dialogue may not always mean <em>finishing</em> the
line's presentation.
</p> <p>
For example, in the <em>Legend of Zelda</em> series of games, lines
of dialogue are displayed one character at a time in a text box,
until the line has finished appearing. At this point, the text box
displays a button to continue; when the user presses the primary
input button (typically the <code>A</code> button), the line is dismissed.
However, if this button is pressed <em>while the line is still
appearing</em>, the rest of the line appears all at once, and the
button appears. Finally, if a secondary input button (typically the
<code>B</code> button) is pressed at any point, the line is
<em>interrupted</em>, and the dialogue proceeds to the next line
immediately.</p> <p>
<a href="yarn.unity.dialogueviewbase.userrequestedviewadvancement.md">UserRequestedViewAdvancement()</a> is designed to give your
Dialogue View an opportunity to decide whether it wants to interrupt
the entire line for all views, or simply speed up the delivery of
<em>this</em> view.
</p> <p>
{% hint style="note" %}
The default implementation of this method does
nothing.
{% endhint %}
</p>

