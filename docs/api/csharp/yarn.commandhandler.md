# CommandHandler

Delegate in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue delivers a  [Command](yarn.command.md) .


```csharp
public delegate void CommandHandler(Command command);
```

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Command](/docs/api/csharp/yarn.command.md) command|The  [Command](yarn.command.md)  that has been delivered.|

## See Also

* [LineHandler](/docs/api/csharp/yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a  [Line](yarn.line.md) .
* [OptionsHandler](/docs/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  [OptionSet](yarn.optionset.md) .
* [NodeStartHandler](/docs/api/csharp/yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [NodeCompleteHandler](/docs/api/csharp/yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [DialogueCompleteHandler](/docs/api/csharp/yarn.dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

