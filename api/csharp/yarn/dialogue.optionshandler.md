# Dialogue.OptionsHandler Property

Gets or sets the [`OptionsHandler`](/api/csharp/yarn/optionshandler.md) that is
called when a set of options are ready to be shown to the user.


```csharp
public OptionsHandler OptionsHandler { get; set; }
```
## Remarks

The Options Handler delivers an [`OptionSet`](/api/csharp/yarn/optionset.md) to the
game. Before [`Continue()`](/api/csharp/yarn/dialogue.continue.md) can be called to resume
execution, [`SetSelectedOption(Int32)`](/api/csharp/yarn/dialogue.setselectedoption-system.int32-.md) must be called to
indicate which [`OptionSet.Option`](/api/csharp/yarn/optionset.option.md) was selected by
the user. If [`SetSelectedOption(Int32)`](/api/csharp/yarn/dialogue.setselectedoption-system.int32-.md) is not called, an
exception is thrown.




## See Also
* [`OptionsHandler`](/api/csharp/yarn/optionshandler.md): 
Represents the method that is called when the Dialogue delivers an
[`OptionSet`](/api/csharp/yarn/optionset.md).

## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L467), line 467.
