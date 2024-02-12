# UserRequestedViewAdvancement()

Method in [LineView](./)

## Summary

Called by [DialogueAdvanceInput](../yarn.unity.dialogueadvanceinput/) to signal that the user has requested that the dialogue advance.

```csharp
public override void UserRequestedViewAdvancement()
```

## Remarks

When this method is called, the Dialogue View should advance the dialogue. Advancing the dialogue can mean different things, depending on the nature of the dialogue view, and its current state.

In many situations, if the Dialogue View hasn't yet finished presenting its line (that is, the [RunLine(LocalizedLine,Action)](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.runline.md) method has been called, but it hasn't yet called its completion handler), it's sufficient to call the [requestInterrupt](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.requestinterrupt.md) method, which tells the Dialogue Runner to interrupt the current line.

'Advancing' the dialogue may not always mean _finishing_ the line's presentation.

For example, in the _Legend of Zelda_ series of games, lines of dialogue are displayed one character at a time in a text box, until the line has finished appearing. At this point, the text box displays a button to continue; when the user presses the primary input button (typically the `A` button), the line is dismissed. However, if this button is pressed _while the line is still appearing_, the rest of the line appears all at once, and the button appears. Finally, if a secondary input button (typically the `B` button) is pressed at any point, the line is _interrupted_, and the dialogue proceeds to the next line immediately.

[UserRequestedViewAdvancement()](../yarn.unity.dialogueviewbase/yarn.unity.dialogueviewbase.userrequestedviewadvancement.md) is designed to give your Dialogue View an opportunity to decide whether it wants to interrupt the entire line for all views, or simply speed up the delivery of _this_ view.

{% hint style="info" %}
The default implementation of this method does nothing.
{% endhint %}
