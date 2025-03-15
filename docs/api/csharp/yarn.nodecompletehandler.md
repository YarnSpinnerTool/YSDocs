# NodeCompleteHandler

Delegate in [Yarn](yarn.md)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the Dialogue reaches the end of a node.

```csharp
public delegate void NodeCompleteHandler(string completedNodeName);
```

## Remarks

This method may be called multiple times over the course of code execution. A node being complete does not necessarily represent the end of the conversation.

## Parameters

| Name                       | Description           |
| -------------------------- | --------------------- |
| `string` completedNodeName | The name of the node. |

## See Also

* [LineHandler](yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a [Line](yarn.line.md) .
* [OptionsHandler](yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an [OptionSet](yarn.optionset.md) .
* [CommandHandler](yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a [Command](yarn.command.md) .
* [NodeStartHandler](yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [DialogueCompleteHandler](yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.
