# autoAdvance

Field in [LinePresenter](yarn.unity.linepresenter.md)

## Summary

Controls whether this Line View will automatically to the Dialogue\
Runner that the line is complete as soon as the line has finished\
appearing.

```csharp
public bool autoAdvance = false;
```

## Remarks

If this value is true, the Line View will

{% hint style="info" %}
The [DialogueRunner](yarn.unity.dialoguerunner.md) will not\
proceed to the next piece of content (e.g. the next line, or the\
next options) until all Dialogue Presenters have reported that they have\
finished presenting their lines. If a [LinePresenter](yarn.unity.linepresenter.md)\
doesn't report that it's finished until it receives input, the [DialogueRunner](yarn.unity.dialoguerunner.md) will end up pausing.

This is useful for games in which you want the player to be able to\
read lines of dialogue at their own pace, and give them control over\
when to advance to the next line.
{% endhint %}
