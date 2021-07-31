# OptionsHandler

Represents the method that is called when the Dialogue delivers an [`OptionSet`](optionset/).

```csharp
public delegate void OptionsHandler(OptionSet options);
```

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`OptionSet`](optionset/) options | The [`OptionSet`](optionset/) that has been delivered. |

## See Also

* [`LineHandler`](linehandler.md): Represents the method that is called when the Dialogue delivers a [`Line`](line/).
* [`CommandHandler`](commandhandler.md): Represents the method that is called when the Dialogue delivers a [`Command`](command/).
* [`NodeStartHandler`](nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [`NodeCompleteHandler`](nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.
* [`DialogueCompleteHandler`](dialoguecompletehandler.md): Represents the method that is called when the dialogue has reached its end, and no more code remains to be run.

## Namespace

[`Yarn`](./)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L313), line 313.

