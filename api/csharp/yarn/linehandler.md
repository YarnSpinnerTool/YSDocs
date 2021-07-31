# LineHandler

Represents the method that is called when the Dialogue delivers a [`Line`](line/).

```csharp
public delegate void LineHandler(Line line);
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Line`](line/) line | The [`Line`](line/) that has been delivered. |

## See Also

* [`OptionsHandler`](optionshandler.md): Represents the method that is called when the Dialogue delivers an [`OptionSet`](optionset/).
* [`CommandHandler`](commandhandler.md): Represents the method that is called when the Dialogue delivers a [`Command`](command/).
* [`NodeStartHandler`](nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [`NodeCompleteHandler`](nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [`DialogueCompleteHandler`](dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

## Namespace

[`Yarn`](./)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L300), line 300.

