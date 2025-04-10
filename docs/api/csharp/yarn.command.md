# Command

Struct in [Yarn](yarn.md)

Inherits from `System.ValueType`

## Summary

A command, sent from the [Dialogue](yarn.dialogue.md) to the game.

```csharp
public struct Command
```

## Remarks

You do not create instances of this struct yourself. They are created by the [Dialogue](yarn.dialogue.md) during program execution.

## Properties

| Name                         | Description                   |
| ---------------------------- | ----------------------------- |
| [Text](yarn.command.text.md) | Gets the text of the command. |

## See Also

* [Dialogue.CommandHandler](yarn.dialogue.commandhandler.md): Gets or sets the [CommandHandler](yarn.commandhandler.md) that is called when a command is to be delivered to the game.
