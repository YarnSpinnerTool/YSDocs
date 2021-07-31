# Continue\(\)

Starts, or continues, execution of the current Program.

```csharp
public void Continue()
```

## Remarks

This method repeatedly executes instructions until one of the following conditions is encountered:

* The [`LineHandler`](dialogue.linehandler.md) or [`CommandHandler`](dialogue.commandhandler.md)

  is called. After calling either of these handlers, the Dialogue

  will wait until [`Continue()`](dialogue.continue.md) is called. Continue may

  be called from inside the [`LineHandler`](dialogue.linehandler.md) or [`CommandHandler`](dialogue.commandhandler.md), or may be called at any future time. \*

  The [`OptionsHandler`](dialogue.optionshandler.md) is called. When this occurs,

  the Dialogue is waiting for the user to specify which of the

  options has been selected, and [`SetSelectedOption(Int32)`](dialogue.setselectedoption-system.int32.md) must be called before [`Continue()`](dialogue.continue.md) is called again.\) \* The Program reaches its

  end. When this occurs, [`SetNode(String)`](dialogue.setnode-system.string.md) must be

  called before [`Continue()`](dialogue.continue.md) is called again. \* An

  error occurs while executing the Program.

This method has no effect if it is called while the [`Dialogue`](./) is currently in the process of executing instructions.

## See Also

* [`LineHandler`](../linehandler.md): Represents the method that is called when the Dialogue delivers a [`Line`](../line/).
* [`OptionsHandler`](../optionshandler.md): Represents the method that is called when the Dialogue delivers an [`OptionSet`](../optionset/).
* [`CommandHandler`](../commandhandler.md): Represents the method that is called when the Dialogue delivers a [`Command`](../command/).
* [`NodeCompleteHandler`](../nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [`DialogueCompleteHandler`](../dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L695), line 695.

