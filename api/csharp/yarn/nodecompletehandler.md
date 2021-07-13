# NodeCompleteHandler Delegate

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
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) completedNodeName|The name of the node.|


## See Also
* [`LineHandler`](/api/csharp/yarn/linehandler.md): 
Represents the method that is called when the Dialogue delivers a
[`Line`](/api/csharp/yarn/line.md).

* [`OptionsHandler`](/api/csharp/yarn/optionshandler.md): 
Represents the method that is called when the Dialogue delivers an
[`OptionSet`](/api/csharp/yarn/optionset.md).

* [`CommandHandler`](/api/csharp/yarn/commandhandler.md): 
Represents the method that is called when the Dialogue delivers a
[`Command`](/api/csharp/yarn/command.md).

* [`NodeStartHandler`](/api/csharp/yarn/nodestarthandler.md): 
Represents the method that is called when the Dialogue begins
executing a node.

* [`DialogueCompleteHandler`](/api/csharp/yarn/dialoguecompletehandler.md): 
Represents the method that is called when the dialogue has reached
its end, and no more code remains to be run.

## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L343), line 343.
