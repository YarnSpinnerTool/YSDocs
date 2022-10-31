# MarkupParseResult.TryGetAttributeWithName(string,MarkupAttribute)

Method in [MarkupParseResult](api/csharp/yarn.markup.markupparseresult.md)

## Summary


Gets the first attribute with the specified name, if present.


```csharp
public bool TryGetAttributeWithName(string name, out MarkupAttribute attribute)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the attribute to get.|
|[Yarn.Markup.MarkupAttribute](api/csharp/yarn.markup.markupattribute.md) attribute|When this method returns, contains the attribute with the specified name, if the attribute is found; otherwise, the default  <a href="yarn.markup.markupattribute.md">MarkupAttribute</a> . This parameter is passed uninitialized.|

## Returns

<code>true</code>  if the  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  contains an attribute with the
specified name; otherwise,  <code>false</code> .

