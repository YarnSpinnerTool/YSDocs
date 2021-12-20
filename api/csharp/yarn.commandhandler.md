# CommandHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue delivers a
<a href="yarn.command.md">Command</a> .


```csharp
public delegate void CommandHandler(Command command);
```

## Parameters

|Name|Description|
|:---|:---|
|command|The  <a href="yarn.command.md">Command</a>  that has been delivered.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md)
* [OptionsHandler](/api/csharp/yarn.optionshandler.md)
* [NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)

