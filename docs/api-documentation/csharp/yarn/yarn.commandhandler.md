# CommandHandler

Delegate in [Yarn](./)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the Dialogue delivers a [Command](yarn.command/) .

```csharp
public delegate void CommandHandler(Command command);
```

## Parameters

| Name                                  | Description                                           |
| ------------------------------------- | ----------------------------------------------------- |
| [Yarn.Command](yarn.command/) command | The [Command](yarn.command/) that has been delivered. |

## See Also

* [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line/) .
* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset/) .
* [NodeStartHandler](yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
