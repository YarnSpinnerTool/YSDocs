# onLineUpdate

A [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md) that is called when the visible part of the line's localised text changes.

```csharp
public DialogueRunner.StringUnityEvent onLineUpdate
```

## Remarks

The  parameter that this event receives is the text that should be displayed to the user. Use this method to display line text to the user.

The [`DialogueUI`](./) class gradually reveals the localised text of the , at a rate of [`textSpeed`](dialogueui.textspeed.md) seconds per character. [`onLineUpdate`](dialogueui.onlineupdate.md) will be called multiple times, each time with more text; the final call to [`onLineUpdate`](dialogueui.onlineupdate.md) will have the entire text of the line.

If the line's Status becomes [`Interrupted`](../linestatus/linestatus.interrupted.md), which indicates that the user has requested that the Dialogue UI skip to the end of the line, [`onLineUpdate`](dialogueui.onlineupdate.md) will be called once more, to display the entire text.

If [`textSpeed`](dialogueui.textspeed.md) is `0`, [`onLineUpdate`](dialogueui.onlineupdate.md) will be called just once, to display the entire text all at once.

After the final call to [`onLineUpdate`](dialogueui.onlineupdate.md), [`onTextFinishDisplaying`](dialogueui.ontextfinishdisplaying.md) will be called to indicate that the line has finished appearing, followed by [`onLineFinishDisplaying`](dialogueui.onlinefinishdisplaying.md).

## See Also

* [`textSpeed`](dialogueui.textspeed.md): How quickly to show the text, in seconds per character
* [`onTextFinishDisplaying`](dialogueui.ontextfinishdisplaying.md): A  that is called when the line has finished being displayed by this view.
* [`onLineFinishDisplaying`](dialogueui.onlinefinishdisplaying.md): A  that is called when a line has finished being delivered on all views.
* [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md): A type of  that takes a single string parameter.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L213), line 213.

