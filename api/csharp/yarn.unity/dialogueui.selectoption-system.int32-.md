# DialogueUI.SelectOption Method

Signals that the user has selected an option.


```csharp
public void SelectOption(int optionID)
```
## Remarks

This method is called by the <see cref="!:Button"></see>s in the [`optionButtons`](/api/csharp/yarn.unity/dialogueui.optionbuttons.md) list when clicked.

If you prefer, you can also call this method directly.


## Parameters
|Parameter|Description|
|:---|:---|
|[`Int32`](https://docs.microsoft.com/dotnet/api/System.Int32) optionID|The <see cref="!:OptionSet.Option.ID"></see> of the <see cref="!:OptionSet.Option"></see> that was selected.|


## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Views/DialogueUI.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Views/DialogueUI.cs#L497), line 497.
