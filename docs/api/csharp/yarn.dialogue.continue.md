# Dialogue.Continue()

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Starts, or continues, execution of the current Program.


```csharp
public void Continue()
```

## Remarks

<p>
This method repeatedly executes instructions until one of the
following conditions is encountered:
</p> <ul type="bullet">
<li>The [CommandHandler](yarn.dialogue.linehandler.md">LineHandler</a> or <a href="yarn.dialogue.commandhandler.md)
is called. After calling either of these handlers, the Dialogue will
wait until [Continue()](yarn.dialogue.continue.md) is called. Continue may be called
from inside the [CommandHandler](yarn.dialogue.linehandler.md">LineHandler</a> or <a href="yarn.dialogue.commandhandler.md), or may be called at any future time.</li>
<li>The [OptionsHandler](yarn.dialogue.optionshandler.md) is called. When this occurs,
the Dialogue is waiting for the user to specify which of the options
has been selected, and [SetSelectedOption(int)](yarn.dialogue.setselectedoption.md) must be
called before [Continue()](yarn.dialogue.continue.md) is called again.)</li>
<li>The Program reaches its end. When this occurs, [Continue()](yarn.dialogue.setnode.md">SetNode(string)</a> must be called before <a href="yarn.dialogue.continue.md) is called again.</li>
<li>An error occurs while executing the Program.</li>
</ul> <p>This method has no effect if it is called while the [Dialogue](yarn.dialogue.md) is currently in the process of executing
instructions.</p>

## See Also

* [LineHandler](/docs/api/csharp/yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a  [Line](yarn.line.md) .
* [OptionsHandler](/docs/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  [OptionSet](yarn.optionset.md) .
* [CommandHandler](/docs/api/csharp/yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a  [Command](yarn.command.md) .
* [NodeCompleteHandler](/docs/api/csharp/yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](/docs/api/csharp/yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

