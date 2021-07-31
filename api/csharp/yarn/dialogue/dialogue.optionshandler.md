# OptionsHandler

Gets or sets the [`OptionsHandler`](../optionshandler.md) that is called when a set of options are ready to be shown to the user.

```csharp
public OptionsHandler OptionsHandler { get; set; }
```

## Remarks

The Options Handler delivers an [`OptionSet`](../optionset/) to the game. Before [`Continue()`](dialogue.continue.md) can be called to resume execution, [`SetSelectedOption(Int32)`](dialogue.setselectedoption-system.int32.md) must be called to indicate which [`OptionSet.Option`](../optionset.option/) was selected by the user. If [`SetSelectedOption(Int32)`](dialogue.setselectedoption-system.int32.md) is not called, an exception is thrown.

## See Also

* [`OptionsHandler`](../optionshandler.md): 

  Represents the method that is called when the Dialogue delivers an

  [`OptionSet`](../optionset/).

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L467), line 467.

