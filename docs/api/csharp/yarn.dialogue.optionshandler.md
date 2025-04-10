# OptionsHandler

Property in [Dialogue](yarn.dialogue.md)

## Summary

Gets or sets the [OptionsHandler](yarn.optionshandler.md) that is called when a set of options are ready to be shown to the user.

```csharp
public OptionsHandler OptionsHandler
{
            get; set; }
```

## Remarks

The Options Handler delivers an [OptionSet](yarn.optionset.md) to the game. Before [Continue()](yarn.dialogue.continue.md) can be called to resume execution, [SetSelectedOption(int)](yarn.dialogue.setselectedoption.md) must be called to indicate which [Option](yarn.optionset.option.md) was selected by the user. If [SetSelectedOption(int)](yarn.dialogue.setselectedoption.md) is not called, an exception is thrown.
