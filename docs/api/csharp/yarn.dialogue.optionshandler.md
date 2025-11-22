# Dialogue.OptionsHandler

Property in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets or sets the  <a href="yarn.optionshandler.md">OptionsHandler</a>  that is called
when a set of options are ready to be shown to the user.


```csharp
public OptionsHandler? OptionsHandler { get; set; }
```

## Remarks


The Options Handler delivers an  <a href="yarn.optionset.md">OptionSet</a>  to the game.
Before  <a href="yarn.dialogue.continue.md">Continue()</a>  can be called to resume execution,
<a href="yarn.dialogue.setselectedoption.md">SetSelectedOption(int)</a>  must be called to indicate which
<a href="yarn.optionset.option.md">Option</a>  was selected by the user. If  <a href="yarn.dialogue.setselectedoption.md">SetSelectedOption(int)</a>  is not called, an exception is thrown.


