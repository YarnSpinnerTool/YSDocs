# DialogueViewBase.requestInterrupt

Field in [DialogueViewBase](/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


Represents the method that should be called when this view wants the
line to be interrupted.


```csharp
public Action requestInterrupt;
```

## Remarks

<p>
{% hint style="info" %}
This value is set by the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> class during initial setup. Do not modify
this value yourself.

{% endhint %}
</p> <p>
When this method is called, the Dialogue Runner that has this
Dialogue View in its <a href="yarn.unity.dialoguerunner.dialogueviews.md">dialogueViews</a> list
will call <a href="yarn.unity.dialogueviewbase.interruptline.md">InterruptLine(LocalizedLine,Action)</a> on any
view that has not yet finished presenting its line.
</p> <p>
A Dialogue View can call this method to signal to the Dialogue
Runner that the current line should be interrupted. This is usually
done when it receives some input that the user wants to skip to the
next line of dialogue.
</p>

