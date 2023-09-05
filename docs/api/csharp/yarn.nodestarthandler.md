# NodeStartHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue begins executing
a node.


```csharp
public delegate void NodeStartHandler(string startedNodeName);
```

## Parameters

|Name|Description|
|:---|:---|
|`string` startedNodeName|The name of the node.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a  <a href="yarn.line.md">Line</a> .
* [OptionsHandler](/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  <a href="yarn.optionset.md">OptionSet</a> .
* [CommandHandler](/api/csharp/yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a  <a href="yarn.command.md">Command</a> .
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

