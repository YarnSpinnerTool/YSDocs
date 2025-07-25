# ILineProvider

Interface in [Yarn.Unity](yarn.unity.md)

## Summary

Contains methods for retrieving user-facing localized content, given\
non-localized line IDs.

```csharp
public interface ILineProvider
```

## Methods

| Name                                                                                                                         | Description                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [DeregisterMarkerProcessor(string)](yarn.unity.ilineprovider.deregistermarkerprocessor.md)                                   | Removes all marker processors that handle markers named `attributeName` .                                     |
| [GetLocalizedLineAsync(Line,CancellationToken)](yarn.unity.ilineprovider.getlocalizedlineasync.md)                           | Prepares and returns a [LocalizedLine](yarn.unity.localizedline.md) from the specified [Line](yarn.line.md) . |
| [PrepareForLinesAsync(IEnumerable,CancellationToken)](yarn.unity.ilineprovider.prepareforlinesasync.md)                      | Signals to the line provider that lines with the provided line IDs may be presented shortly.                  |
| [RegisterMarkerProcessor(string,Yarn.Markup.IAttributeMarkerProcessor)](yarn.unity.ilineprovider.registermarkerprocessor.md) | Adds a new marker processor to the line provider.                                                             |

## Properties

| Name                                                   | Description                                                                                            |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| [LocaleCode](yarn.unity.ilineprovider.localecode.md)   | Gets the line provider's current locale identifier, as a BCP-47 code.                                  |
| [YarnProject](yarn.unity.ilineprovider.yarnproject.md) | The [YarnProject](yarn.unity.ilineprovider.yarnproject.md) that contains the localized data for lines. |
