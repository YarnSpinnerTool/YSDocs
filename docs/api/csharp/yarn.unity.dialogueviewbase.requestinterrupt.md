# requestInterrupt

Field in [DialogueViewBase](yarn.unity.dialogueviewbase.md)

## Summary

Represents the method that should be called when this view wants the line to be interrupted.

```csharp
public Action requestInterrupt;
```

## Remarks

{% hint style="info" %}
This value is set by the [DialogueRunner](yarn.unity.dialoguerunner.md) class during initial setup. Do not modify this value yourself.
{% endhint %}

When this method is called, the Dialogue Runner that has this Dialogue View in its `Yarn.Unity.DialogueRunner.dialogueViews` list will call [InterruptLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.interruptline.md) on any view that has not yet finished presenting its line.

A Dialogue View can call this method to signal to the Dialogue Runner that the current line should be interrupted. This is usually done when it receives some input that the user wants to skip to the next line of dialogue.
