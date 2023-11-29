# NodeCompleteHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue reaches the end
of a node.


```csharp
public delegate void NodeCompleteHandler(string completedNodeName);
```

## Remarks


This method may be called multiple times over the course of code
execution. A node being complete does not necessarily represent the end
of the conversation.


## Parameters

|Name|Description|
|:---|:---|
|`string` completedNodeName|The name of the node.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a  <a href="yarn.line.md">Line</a> .
* [OptionsHandler](/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  <a href="yarn.optionset.md">OptionSet</a> .
* [CommandHandler](/api/csharp/yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a  <a href="yarn.command.md">Command</a> .
* [NodeStartHandler](/api/csharp/yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

