# GetLocalizedLine(Yarn.Line)

Method in [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md)

## Summary

Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified [Line](yarn.line.md) .

```csharp
public abstract LocalizedLine GetLocalizedLine(Yarn.Line line);
```

## Remarks

This method should not be called if [LinesAvailable](yarn.unity.lineproviderbehaviour.linesavailable.md) returns `false` .

## Parameters

| Name                           | Description                                                                                |
| ------------------------------ | ------------------------------------------------------------------------------------------ |
| [Yarn.Line](yarn.line.md) line | The [Line](yarn.line.md) to produce the [LocalizedLine](yarn.unity.localizedline.md) from. |

## Returns

A localized line, ready to be presented to the player.
