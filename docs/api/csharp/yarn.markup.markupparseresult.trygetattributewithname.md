# MarkupParseResult.TryGetAttributeWithName(string,MarkupAttribute)

Method in [MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md)

## Summary


Gets the first attribute with the specified name, if present.


```csharp
public readonly bool TryGetAttributeWithName(string name, out MarkupAttribute attribute)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the attribute to get.|
|[Yarn.Markup.MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md) attribute|When this method returns, contains the attribute with the specified name, if the attribute is found; otherwise, the default  [MarkupAttribute](yarn.markup.markupattribute.md) . This parameter is passed uninitialized.|

## Returns

`true`  if the  [MarkupParseResult](yarn.markup.markupparseresult.md)  contains an attribute with the
specified name; otherwise,  `false` .

