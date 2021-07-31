# CommandHandler

Represents the method that is called when the Dialogue delivers a [`Command`](command/).

```csharp
public delegate void CommandHandler(Command command);
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Command`](command/) command | The [`Command`](command/) that has been delivered. |

## See Also

* [`LineHandler`](linehandler.md): Represents the method that is called when the Dialogue delivers a [`Line`](line/).
* [`OptionsHandler`](optionshandler.md): Represents the method that is called when the Dialogue delivers an [`OptionSet`](optionset/).
* [`NodeStartHandler`](nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [`NodeCompleteHandler`](nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [`DialogueCompleteHandler`](dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

## Namespace

[`Yarn`](./)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L326), line 326.

