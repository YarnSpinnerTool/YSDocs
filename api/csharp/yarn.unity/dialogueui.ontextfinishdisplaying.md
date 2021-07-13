# DialogueUI.onTextFinishDisplaying Field

A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called
when the line has finished being displayed by this view.


```csharp
public UnityEngine.Events.UnityEvent onTextFinishDisplaying
```
## Remarks

This method is called after [`onLineUpdate`](/api/csharp/yarn.unity/dialogueui.onlineupdate.md). Use
this method to display UI elements like a "continue" button. 

If there are multiple views displaying this line, this method
may be called some time before [`onLineFinishDisplaying`](/api/csharp/yarn.unity/dialogueui.onlinefinishdisplaying.md)
is called.




## See Also
* [`onLineUpdate`](/api/csharp/yarn.unity/dialogueui.onlineupdate.md): 
A [`DialogueRunner.StringUnityEvent`](/api/csharp/yarn.unity/dialoguerunner.stringunityevent.md) that is called
when the visible part of the line's localised text changes.

* [`onLineFinishDisplaying`](/api/csharp/yarn.unity/dialogueui.onlinefinishdisplaying.md): 
A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called
when a line has finished being delivered on all views.

<div class="class-metadata">

Parent: [`DialogueUI`](/api/csharp/yarn.unity/dialogueui.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L162), line 162.
