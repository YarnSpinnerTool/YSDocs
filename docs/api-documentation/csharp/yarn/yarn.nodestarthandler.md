# NodeStartHandler

Delegate in [Yarn](./)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the Dialogue begins executing a node.

```csharp
public delegate void NodeStartHandler(string startedNodeName);
```

## Parameters

| Name                     | Description           |
| ------------------------ | --------------------- |
| `string` startedNodeName | The name of the node. |

## See Also

* [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line/) .
* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset/) .
* [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command/) .
* [NodeCompleteHandler](yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
