# DialogueUI.onOptionsEnd Field

A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called
when an option has been selected, and the [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md) should be hidden.


```csharp
public UnityEngine.Events.UnityEvent onOptionsEnd
```
## Remarks

This method is called after one of the [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md) has been clicked, or the [`SelectOption(Int32)`](/api/csharp/yarn.unity/dialogueui.selectoption-system.int32-.md) method has been called.

Use this method to hide all of the [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md),
such as by disabling the object they're contained in. (The
DialogueUI won't hide them for you individually.)




<div class="class-metadata">

Parent: [`DialogueUI`](/api/csharp/yarn.unity/dialogueui.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L262), line 262.
