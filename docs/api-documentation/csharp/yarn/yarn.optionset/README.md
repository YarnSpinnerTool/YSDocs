# OptionSet

Struct in [Yarn](../)

Inherits from `System.ValueType`

## Summary

A set of [Option](yarn.optionset.option/) s, sent from the [Dialogue](../yarn.dialogue/) to the game.

```csharp
public struct OptionSet
```

## Remarks

You do not create instances of this struct yourself. They are created by the [Dialogue](../yarn.dialogue/) during program execution.

## Properties

| Name                                 | Description                                                                       |
| ------------------------------------ | --------------------------------------------------------------------------------- |
| [Options](yarn.optionset.options.md) | Gets the [Option](yarn.optionset.option/) s that should be presented to the user. |

## Structs

| Name                             | Description                            |
| -------------------------------- | -------------------------------------- |
| [Option](yarn.optionset.option/) | An option to be presented to the user. |

## See Also

* [Dialogue.OptionsHandler](../yarn.dialogue/yarn.dialogue.optionshandler.md): Gets or sets the [OptionsHandler](../yarn.optionshandler.md) that is called when a set of options are ready to be shown to the user.
