# OptionSet

A set of [`OptionSet.Option`](../optionset.option/)s, sent from the [`Dialogue`](../dialogue/) to the game.

```csharp
public struct OptionSet
```

## Remarks

You do not create instances of this struct yourself. They are created by the [`Dialogue`](../dialogue/) during program execution.

## Properties

| Name | Description |
| :--- | :--- |
| [`Options`](optionset.options.md) | Gets the [`OptionSet.Option`](../optionset.option/)s that should be presented to the user. |

## See Also

* [`OptionsHandler`](../dialogue/dialogue.optionshandler.md): 

  Gets or sets the [`OptionsHandler`](../optionshandler.md) that is

  called when a set of options are ready to be shown to the user.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L85), line 85.

