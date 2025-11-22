# SetSelectedOption(int)

Method in [Dialogue](yarn.dialogue.md)

## Summary

Signals to the [Dialogue](yarn.dialogue.md) that the user has selected a\
specified [Option](yarn.optionset.option.md) .

```csharp
public void SetSelectedOption(int selectedOptionID)
```

## Remarks

After the Dialogue delivers an [OptionSet](yarn.optionset.md), this method\
must be called before [Continue()](yarn.dialogue.continue.md) is called.

The ID number that should be passed as the parameter to this method\
should be the [ID](yarn.optionset.option.id.md) field in the [Option](yarn.optionset.option.md) that represents the user's selection.

## Parameters

| Name                   | Description                                         |
| ---------------------- | --------------------------------------------------- |
| `int` selectedOptionID | The ID number of the Option that the user selected. |

## See Also

* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset.md) .
* [OptionSet](yarn.optionset.md): A set of [Option](yarn.optionset.option.md) s, sent from the [Dialogue](yarn.dialogue.md) to the game.
* [Dialogue.Continue()](yarn.dialogue.continue.md): Starts, or continues, execution of the current Program.
