# LineHandler

Delegate in [Yarn](./)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the Dialogue delivers a [Line](yarn.line/) .

```csharp
public delegate void LineHandler(Line line);
```

## Parameters

| Name                         | Description                                     |
| ---------------------------- | ----------------------------------------------- |
| [Yarn.Line](yarn.line/) line | The [Line](yarn.line/) that has been delivered. |

## See Also

* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset/) .
* [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command/) .
* [NodeStartHandler](yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
