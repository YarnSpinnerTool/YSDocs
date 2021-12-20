# NodeCompleteHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue reaches the
end of a node.


```csharp
public delegate void NodeCompleteHandler(string completedNodeName);
```

## Remarks


This method may be called multiple times over the course of code
execution. A node being complete does not necessarily represent the
end of the conversation.


## Parameters

|Name|Description|
|:---|:---|
|completedNodeName|The name of the node.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md)
* [OptionsHandler](/api/csharp/yarn.optionshandler.md)
* [CommandHandler](/api/csharp/yarn.commandhandler.md)
* [NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)

