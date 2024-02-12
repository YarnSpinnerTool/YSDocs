# SetSelectedOption(int)

Method in [Dialogue](./)

## Summary

Signals to the [Dialogue](./) that the user has selected a specified [Option](../yarn.optionset/yarn.optionset.option/) .

```csharp
public void SetSelectedOption(int selectedOptionID)
```

## Remarks

After the Dialogue delivers an [OptionSet](../yarn.optionset/), this method must be called before [Continue()](yarn.dialogue.continue.md) is called.

The ID number that should be passed as the parameter to this method should be the [ID](../yarn.optionset/yarn.optionset.option/yarn.optionset.option.id.md) field in the [Option](../yarn.optionset/yarn.optionset.option/) that represents the user's selection.

## Parameters

| Name                   | Description                                         |
| ---------------------- | --------------------------------------------------- |
| `int` selectedOptionID | The ID number of the Option that the user selected. |

## See Also

* [OptionsHandler](../yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](../yarn.optionset/) .
* [OptionSet](../yarn.optionset/): A set of [Option](../yarn.optionset/yarn.optionset.option/) s, sent from the [Dialogue](./) to the game.
* [Dialogue.Continue()](yarn.dialogue.continue.md): Starts, or continues, execution of the current Program.
