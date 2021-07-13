# DialogueUI.onLineEnd Field

A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called
when a line has finished displaying, and should be removed from
the screen.


```csharp
public UnityEngine.Events.UnityEvent onLineEnd
```
## Remarks

This method is called after the line's [`Status`](/api/csharp/yarn.unity/localizedline.status.md)
has changed to [`Ended`](/api/csharp/yarn.unity/linestatus.ended.md).
Use this method to dismiss the line's UI elements.

After this method is called, the next piece of dialogue content
will be presented, or the dialogue will end.




## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L229), line 229.
