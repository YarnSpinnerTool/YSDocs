# MarkupParseResult.TextForAttribute(MarkupAttribute)

Method in [MarkupParseResult](/api/csharp/yarn.markup.markupparseresult.md)

## Summary


Returns the substring of  <a href="yarn.markup.markupparseresult.text.md">Text</a>  covered by
<code>attribute</code>  Position and Length properties.


```csharp
public string TextForAttribute(MarkupAttribute attribute)
```

## Remarks


If the attribute's  <a href="yarn.markup.markupattribute.length.md">Length</a> 
property is zero, this method returns the empty string.

This method does not check to see if  <code>attribute</code>  is an attribute belonging to this
MarkupParseResult. As a result, if you pass an attribute that
doesn't belong, it may describe a range of text that does not
appear in  <a href="yarn.markup.markupparseresult.text.md">Text</a> . If this occurs, an  <code>System.IndexOutOfRangeException</code>  will be thrown.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Markup.MarkupAttribute](/api/csharp/yarn.markup.markupattribute.md) attribute|The attribute to get the text for.|

## Returns

The text contained within the attribute.

