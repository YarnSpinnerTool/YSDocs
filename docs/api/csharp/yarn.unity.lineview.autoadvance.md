# LineView.autoAdvance

Field in [LineView](/docs/api/csharp/yarn.unity.lineview.md)

## Summary


Controls whether this Line View will wait for user input before
indicating that it has finished presenting a line.


```csharp
public bool autoAdvance = false;
```

## Remarks

<p>
If this value is true, the Line View will not report that it has
finished presenting its lines. Instead, it will wait until the <a href="yarn.unity.lineview.userrequestedviewadvancement.md">UserRequestedViewAdvancement()</a> method is called.
</p> <p>
{% hint style="note" %}
<p>The <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will not
proceed to the next piece of content (e.g. the next line, or the
next options) until all Dialogue Views have reported that they have
finished presenting their lines. If a <a href="yarn.unity.lineview.md">LineView</a> doesn't
report that it's finished until it receives input, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will end up pausing.</p><p>
This is useful for games in which you want the player to be able to
read lines of dialogue at their own pace, and give them control over
when to advance to the next line.</p>
{% endhint %}
</p>

