# onOptionsStart

A  that is called when an  has been displayed to the user.

```csharp
public UnityEngine.Events.UnityEvent onOptionsStart
```

## Remarks

Before this method is called, the s in [`optionButtons`](dialogueui.optionbuttons.md) are enabled or disabled \(depending on how many options there are\), and the  or  is updated with the correct text.

Use this method to ensure that the active [`optionButtons`](dialogueui.optionbuttons.md)s are visible, such as by enabling the object that they're contained in.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L246), line 246.

