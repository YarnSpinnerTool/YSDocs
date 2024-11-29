# ILineProvider

## Summary


Contains methods for retrieving user-facing localized content, given
non-localized line IDs.


```csharp
public interface ILineProvider
```

## Methods

|Name|Description|
|:---|:---|
|[DeregisterMarkerProcessor(string)](/docs/api/csharp/ilineprovider.deregistermarkerprocessor.md)|Removes all marker processors that handle markers named  <code>attributeName</code> .|
|[GetLocalizedLineAsync(Line,CancellationToken)](/docs/api/csharp/ilineprovider.getlocalizedlineasync.md)|Prepares and returns a  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  from the specified <a href="yarn.line.md">Line</a> .|
|[PrepareForLinesAsync(IEnumerable<string>,CancellationToken)](/docs/api/csharp/ilineprovider.prepareforlinesasync.md)|Signals to the line provider that lines with the provided line IDs may be presented shortly.|
|[RegisterMarkerProcessor(string,Yarn.Markup.IAttributeMarkerProcessor)](/docs/api/csharp/ilineprovider.registermarkerprocessor.md)|Adds a new marker processor to the line provider.|

## Properties

|Name|Description|
|:---|:---|
|[LocaleCode](/docs/api/csharp/ilineprovider.localecode.md)|Gets the user's current locale identifier, as a BCP-47 code.|
|[YarnProject](/docs/api/csharp/ilineprovider.yarnproject.md)|The  <a href="ilineprovider.yarnproject.md">YarnProject</a>  that contains the localized data for lines.|

