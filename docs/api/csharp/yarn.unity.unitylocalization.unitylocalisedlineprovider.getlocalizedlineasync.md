# GetLocalizedLineAsync(Line,CancellationToken)

Method in [UnityLocalisedLineProvider](yarn.unity.unitylocalization.unitylocalisedlineprovider.md)

## Summary

Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified[Line](yarn.line.md) .

```csharp
public override async YarnTask<LocalizedLine> GetLocalizedLineAsync(Line line, CancellationToken cancellationToken)
```

## Parameters

| Name                                  | Description                                                                                                              |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| [Yarn.Line](yarn.line.md) line        | The [Line](yarn.line.md) to produce the [LocalizedLine](yarn.unity.localizedline.md) from.                               |
| `CancellationToken` cancellationToken | A cancellation token that indicates whether the process of fetching the localised version of `line` should be cancelled. |

## Returns

A localized line, ready to be presented to the\
player.
