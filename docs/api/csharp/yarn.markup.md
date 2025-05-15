# Yarn.Markup Namespace

## Summary

Contains classes for working with markup in Yarn lines.


## Classes

|Name|Description|
|:---|:---|
|[BuiltInMarkupReplacer](/docs/api/csharp/yarn.markup.builtinmarkupreplacer.md)|A marker processor that handles the built-in markers  `[select]` `[plural]` , and  `[ordinal]` .|
|[LineParser](/docs/api/csharp/yarn.markup.lineparser.md)|Parses text and produces markup information.|
|[MarkupParseException](/docs/api/csharp/yarn.markup.markupparseexception.md)|An exception representing something going wrong when parsing markup.|

## Enums

|Name|Description|
|:---|:---|
|[MarkupValueType](/docs/api/csharp/yarn.markup.markupvaluetype.md)|A type of  [MarkupValue](yarn.markup.markupvalue.md) .|
|[TagType](/docs/api/csharp/yarn.markup.tagtype.md)|A type of  `Yarn.Markup.MarkupAttributeMarker` .|

## Interfaces

|Name|Description|
|:---|:---|
|[IAttributeMarkerProcessor](/docs/api/csharp/yarn.markup.iattributemarkerprocessor.md)|Provides a mechanism for producing replacement text for a marker.|

## Structs

|Name|Description|
|:---|:---|
|[MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md)|Represents a range of text in a marked-up string.|
|[MarkupParseResult](/docs/api/csharp/yarn.markup.markupparseresult.md)|The result of parsing a line of marked-up text.|
|[MarkupProperty](/docs/api/csharp/yarn.markup.markupproperty.md)|A property associated with a  [MarkupAttribute](yarn.markup.markupattribute.md) .|
|[MarkupValue](/docs/api/csharp/yarn.markup.markupvalue.md)|A value associated with a  [MarkupProperty](yarn.markup.markupproperty.md) .|

