# OptionsHandler

Delegate in [Yarn](./)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset/) .

```csharp
public delegate void OptionsHandler(OptionSet options);
```

## Parameters

| Name                                      | Description                                               |
| ----------------------------------------- | --------------------------------------------------------- |
| [Yarn.OptionSet](yarn.optionset/) options | The [OptionSet](yarn.optionset/) that has been delivered. |

## See Also

* [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line/) .
* [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command/) .
* [NodeStartHandler](yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
