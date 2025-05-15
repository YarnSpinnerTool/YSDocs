# Dialogue.SetSelectedOption(int)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Signals to the  [Dialogue](yarn.dialogue.md)  that the user has selected a
specified  [Option](yarn.optionset.option.md) .


```csharp
public void SetSelectedOption(int selectedOptionID)
```

## Remarks

<p>
After the Dialogue delivers an [OptionSet](yarn.optionset.md), this method
must be called before [Continue()](yarn.dialogue.continue.md) is called.
</p> <p>
The ID number that should be passed as the parameter to this method
should be the [Option](yarn.optionset.option.id.md">ID</a> field in the <a href="yarn.optionset.option.md) that represents the user's selection.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`int` selectedOptionID|The ID number of the Option that the user selected.|

## See Also

* [OptionsHandler](/docs/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  [OptionSet](yarn.optionset.md) .
* [OptionSet](/docs/api/csharp/yarn.optionset.md): A set of  [Dialogue](yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md)  to the game.
* [Dialogue.Continue\(\)](/docs/api/csharp/yarn.dialogue.continue.md): Starts, or continues, execution of the current Program.

