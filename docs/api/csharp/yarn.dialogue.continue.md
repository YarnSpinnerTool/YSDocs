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

*   The \[CommandHandler]\(yarn.dialogue.linehandler.md">LineHandler or [LineHandler](yarn.dialogue.commandhandler.md\)%0Ais%20called.%20After%20calling%20either%20of%20these%20handlers,%20the%20Dialogue%20will%0Await%20until%20\[Continue\(\)]\(yarn.dialogue.continue.md\)%20is%20called.%20Continue%20may%20be%20called%0Afrom%20inside%20the%20\[CommandHandler]\(yarn.dialogue.linehandler.md) or [SetNode(string)](yarn.dialogue.commandhandler.md\),%20or%20may%20be%20called%20at%20any%20future%20time.%3C/li%3E%0A%3Cli%3EThe%20\[OptionsHandler]\(yarn.dialogue.optionshandler.md\)%20is%20called.%20When%20this%20occurs,%0Athe%20Dialogue%20is%20waiting%20for%20the%20user%20to%20specify%20which%20of%20the%20options%0Ahas%20been%20selected,%20and%20\[SetSelectedOption\(int\)]\(yarn.dialogue.setselectedoption.md\)%20must%20be%0Acalled%20before%20\[Continue\(\)]\(yarn.dialogue.continue.md\)%20is%20called%20again.\)%3C/li%3E%0A%3Cli%3EThe%20Program%20reaches%20its%20end.%20When%20this%20occurs,%20\[Continue\(\)]\(yarn.dialogue.setnode.md) must be called before

    ### See Also

    * [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line.md) .
    * [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset.md) .
    * [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command.md) .
    * [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
    * [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
