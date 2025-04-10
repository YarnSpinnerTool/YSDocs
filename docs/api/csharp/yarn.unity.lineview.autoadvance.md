# autoAdvance

Field in [LineView](yarn.unity.lineview.md)

## Summary

Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.

```csharp
public bool autoAdvance = false;
```

## Remarks

If this value is true, the Line View will not report that it has finished presenting its lines. Instead, it will wait until the [UserRequestedViewAdvancement()](yarn.unity.lineview.userrequestedviewadvancement.md) method is called.

{% hint style="info" %}
The [DialogueRunner](yarn.unity.dialoguerunner.md) will not proceed to the next piece of content (e.g. the next line, or the next options) until all Dialogue Views have reported that they have finished presenting their lines. If a [LineView](yarn.unity.lineview.md) doesn't report that it's finished until it receives input, the [DialogueRunner](yarn.unity.dialoguerunner.md) will end up pausing.

This is useful for games in which you want the player to be able to read lines of dialogue at their own pace, and give them control over when to advance to the next line.
{% endhint %}
