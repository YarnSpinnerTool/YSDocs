# Command

Struct in [Yarn](/api/csharp/yarn.md)

Inherits from `System.ValueType`

## Summary


A command, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.


```csharp
public struct Command
```

## Remarks


You do not create instances of this struct yourself. They are
created by the  <a href="yarn.dialogue.md">Dialogue</a>  during program execution.


## Properties

|Name|Description|
|:---|:---|
|[Text](/api/csharp/yarn.command.text.md)|Gets the text of the command.|

## See Also

* [CommandHandler](/api/csharp/yarn.dialogue.commandhandler.md): Gets or sets the  <a href="yarn.commandhandler.md">CommandHandler</a>  that is called when a command is to be delivered to the game.

