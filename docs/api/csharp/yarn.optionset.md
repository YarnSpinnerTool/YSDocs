# OptionSet

Struct in [Yarn](yarn.md)

Inherits from `System.ValueType`

## Summary

A set of [Option](yarn.optionset.option.md) s, sent from the [Dialogue](yarn.dialogue.md) to the game.

```csharp
public struct OptionSet
```

## Remarks

You typically do not create instances of this struct yourself. They are\
created by the [Dialogue](yarn.dialogue.md) during program execution.

## Properties

| Name                                 | Description                                                                         |
| ------------------------------------ | ----------------------------------------------------------------------------------- |
| [Options](yarn.optionset.options.md) | Gets the [Option](yarn.optionset.option.md) s that should be presented to the user. |

## Structs

| Name                               | Description                            |
| ---------------------------------- | -------------------------------------- |
| [Option](yarn.optionset.option.md) | An option to be presented to the user. |

## See Also

* [Dialogue.OptionsHandler](yarn.dialogue.optionshandler.md): Gets or sets the [OptionsHandler](yarn.optionshandler.md) that is called when a set of options are ready to be shown to the user.
