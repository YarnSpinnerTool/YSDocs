# Continue()

Method in [Dialogue](yarn.dialogue.md)

## Summary

Starts, or continues, execution of the current Program.

```csharp
public void Continue()
```

## Remarks

This method repeatedly executes instructions until one of the\
following conditions is encountered:

* The [LineHandler](yarn.dialogue.linehandler.md) or [CommandHandler](yarn.dialogue.commandhandler.md)\
  is called. After calling either of these handlers, the Dialogue will\
  wait until [Continue()](yarn.dialogue.continue.md) is called. Continue may be called\
  from inside the [LineHandler](yarn.dialogue.linehandler.md) or [CommandHandler](yarn.dialogue.commandhandler.md), or may be called at any future time.
* The [OptionsHandler](yarn.dialogue.optionshandler.md) is called. When this occurs,\
  the Dialogue is waiting for the user to specify which of the options\
  has been selected, and [SetSelectedOption(int)](yarn.dialogue.setselectedoption.md) must be\
  called before [Continue()](yarn.dialogue.continue.md) is called again.)
* The Program reaches its end. When this occurs, [SetNode(string)](yarn.dialogue.setnode.md) must be called before [Continue()](yarn.dialogue.continue.md) is called again.
* An error occurs while executing the Program.

This method has no effect if it is called while the [Dialogue](yarn.dialogue.md) is currently in the process of executing\
instructions.

## See Also

* [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line.md) .
* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset.md) .
* [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command.md) .
* [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
