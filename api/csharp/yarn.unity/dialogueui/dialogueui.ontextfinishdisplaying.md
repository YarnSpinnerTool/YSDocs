# onTextFinishDisplaying

A  that is called when the line has finished being displayed by this view.

```csharp
public UnityEngine.Events.UnityEvent onTextFinishDisplaying
```

## Remarks

This method is called after [`onLineUpdate`](dialogueui.onlineupdate.md). Use this method to display UI elements like a "continue" button.

If there are multiple views displaying this line, this method may be called some time before [`onLineFinishDisplaying`](dialogueui.onlinefinishdisplaying.md) is called.

## See Also

* [`onLineUpdate`](dialogueui.onlineupdate.md): A [`DialogueRunner.StringUnityEvent`](../dialoguerunner.stringunityevent.md) that is called when the visible part of the line's localised text changes.
* [`onLineFinishDisplaying`](dialogueui.onlinefinishdisplaying.md): A  that is called when a line has finished being delivered on all views.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L162), line 162.

