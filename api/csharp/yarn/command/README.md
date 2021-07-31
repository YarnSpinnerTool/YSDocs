# Command

A command, sent from the [`Dialogue`](../dialogue/) to the game.

```csharp
public struct Command
```

## Remarks

You do not create instances of this struct yourself. They are created by the [`Dialogue`](../dialogue/) during program execution.

## Properties

| Name | Description |
| :--- | :--- |
| [`Text`](command.text.md) | Gets the text of the command. |

## See Also

* [`CommandHandler`](../dialogue/dialogue.commandhandler.md): 

  Gets or sets the [`CommandHandler`](../commandhandler.md) that is

  called when a command is to be delivered to the game.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L171), line 171.

