# SetSelectedOption\(Int32\)

Signals to the [`Dialogue`](./) that the user has selected a specified [`OptionSet.Option`](../optionset.option/).

```csharp
public void SetSelectedOption(int selectedOptionID)
```

## Remarks

After the Dialogue delivers an [`OptionSet`](../optionset/), this method must be called before [`Continue()`](dialogue.continue.md) is called.

The ID number that should be passed as the parameter to this method should be the [`ID`](../optionset.option/optionset.option.id.md) field in the [`OptionSet.Option`](../optionset.option/) that represents the user's selection.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Int32`](https://docs.microsoft.com/dotnet/api/System.Int32) selectedOptionID | The ID number of the Option that the user selected. |

## See Also

* [`OptionsHandler`](../optionshandler.md): Represents the method that is called when the Dialogue delivers an [`OptionSet`](../optionset/).
* [`OptionSet`](../optionset/): A set of [`OptionSet.Option`](../optionset.option/)s, sent from the [`Dialogue`](./) to the game.
* [`Continue()`](dialogue.continue.md): Starts, or continues, execution of the current Program.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L660), line 660.

