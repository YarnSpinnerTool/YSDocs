# NodeStartHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue begins
executing a node.


```csharp
public delegate void NodeStartHandler(string startedNodeName);
```

## Parameters

|Name|Description|
|:---|:---|
|startedNodeName|The name of the node.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md)
* [OptionsHandler](/api/csharp/yarn.optionshandler.md)
* [CommandHandler](/api/csharp/yarn.commandhandler.md)
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)

