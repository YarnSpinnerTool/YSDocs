# DialogueUI.onOptionsStart Field

A <see cref="!:UnityEngine.Events.UnityEvent"></see> that is called
when an <see cref="!:OptionSet"></see> has been displayed to the user.


```csharp
public UnityEngine.Events.UnityEvent onOptionsStart
```
## Remarks

Before this method is called, the <see cref="!:Button"></see>s in [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md) are enabled or disabled (depending on
how many options there are), and the <see cref="!:Text"></see> or <see cref="!:TMPro.TextMeshProUGUI"></see> is updated with the correct
text.

Use this method to ensure that the active [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md)s are visible, such as by enabling the
object that they're contained in.




<div class="class-metadata">

Parent: [`DialogueUI`](/api/csharp/yarn.unity/dialogueui.md), Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L246), line 246.
