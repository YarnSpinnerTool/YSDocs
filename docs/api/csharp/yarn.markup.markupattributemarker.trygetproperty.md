# MarkupAttributeMarker.TryGetProperty(string,MarkupValue)

Method in [MarkupAttributeMarker](/docs/api/csharp/yarn.markup.markupattributemarker.md)

## Summary


Gets the property associated with the specified key, if
present.


```csharp
public bool TryGetProperty(string name, out MarkupValue result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the property to get.|
|[Yarn.Markup.MarkupValue](/docs/api/csharp/yarn.markup.markupvalue.md) result|When this method returns, contains the value associated with the specified key, if the key is found; otherwise, the default  <a href="yarn.markup.markupvalue.md">MarkupValue</a> . This parameter is passed uninitialized.|

## Returns

<code>true</code>  if the  <a href="yarn.markup.markupattributemarker.md">MarkupAttributeMarker</a>  contains an element with the
specified key; otherwise,  <code>false</code> .

