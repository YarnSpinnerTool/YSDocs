# optionButtons

The buttons that let the user choose an option.

```csharp
public List<Button> optionButtons
```

## Remarks

The  objects in this list will be enabled and disabled by the [`DialogueUI`](./). Each button should have as a child object a  or a  as a label; the text of this child object will be updated by the DialogueUI as necessary.

You do not need to configure the On Click action of any of these buttons. The [`DialogueUI`](./) will configure them for you.

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L80), line 80.

