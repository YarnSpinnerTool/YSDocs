# GetLocalizedLine(Yarn.Line)

Method in [LineProviderBehaviour](./)

## Summary

Prepares and returns a [LocalizedLine](../yarn.unity.localizedline/) from the specified [Line](../../yarn/yarn.line/) .

```csharp
public abstract LocalizedLine GetLocalizedLine(Yarn.Line line);
```

## Remarks

This method should not be called if [LinesAvailable](yarn.unity.lineproviderbehaviour.linesavailable.md) returns `false` .

## Parameters

| Name                                    | Description                                                                                          |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| [Yarn.Line](../../yarn/yarn.line/) line | The [Line](../../yarn/yarn.line/) to produce the [LocalizedLine](../yarn.unity.localizedline/) from. |

## Returns

A localized line, ready to be presented to the player.
