# DialogueCompleteHandler

Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

```csharp
public delegate void DialogueCompleteHandler();
```

## See Also

* [`LineHandler`](linehandler.md): Represents the method that is called when the Dialogue delivers a [`Line`](line/).
* [`OptionsHandler`](optionshandler.md): Represents the method that is called when the Dialogue delivers an [`OptionSet`](optionset/).
* [`CommandHandler`](commandhandler.md): Represents the method that is called when the Dialogue delivers a [`Command`](command/).
* [`NodeStartHandler`](nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [`NodeCompleteHandler`](nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.

## Namespace

[`Yarn`](./)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L366), line 366.

