# ILineProvider

Interface in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

## Summary


Contains methods for retrieving user-facing localized content, given
non-localized line IDs.


```csharp
public interface ILineProvider
```

## Methods

|Name|Description|
|:---|:---|
|[DeregisterMarkerProcessor(string)](/docs/api/csharp/yarn.unity.ilineprovider.deregistermarkerprocessor.md)|Removes all marker processors that handle markers named  <code>attributeName</code> .|
|[GetLocalizedLineAsync(Line,CancellationToken)](/docs/api/csharp/yarn.unity.ilineprovider.getlocalizedlineasync.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified <a href="yarn.line.md">Line</a> .|
|[PrepareForLinesAsync(IEnumerable<string>,CancellationToken)](/docs/api/csharp/yarn.unity.ilineprovider.prepareforlinesasync.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[RegisterMarkerProcessor(string,Yarn.Markup.IAttributeMarkerProcessor)](/docs/api/csharp/yarn.unity.ilineprovider.registermarkerprocessor.md)|Adds a new marker processor to the line provider.|

## Properties

|Name|Description|
|:---|:---|
|[LocaleCode](/docs/api/csharp/yarn.unity.ilineprovider.localecode.md)|Gets the line provider's current locale identifier, as a BCP-47 code.|
|[YarnProject](/docs/api/csharp/yarn.unity.ilineprovider.yarnproject.md)|The  <a href="yarn.unity.ilineprovider.yarnproject.md">YarnProject</a>  that contains the localized data for lines.|

