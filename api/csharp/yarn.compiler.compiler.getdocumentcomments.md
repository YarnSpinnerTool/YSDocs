# Compiler.GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)

Method in [Compiler](/api/csharp/yarn.compiler.compiler.md)

## Summary


Gets the text of the documentation comments that either immediately
precede  <code>context</code> , or are on the same line as
<code>context</code> .


```csharp
public static string GetDocumentComments(CommonTokenStream tokens, ParserRuleContext context, bool allowCommentsAfter = true)
```

## Remarks


Documentation comments begin with a triple-slash ( <code>///</code> ), and
are used to describe variable declarations. If documentation
comments precede a declaration (that is, they're not on the same
line as the declaration), then they may span multiple lines, as long
as each line begins with a triple-slash.


## Parameters

|Name|Description|
|:---|:---|
|`Antlr4.Runtime.CommonTokenStream` tokens|The token stream to search.|
|`Antlr4.Runtime.ParserRuleContext` context|The parser rule context to get documentation comments for.|
|`bool` allowCommentsAfter|If true, this method will search for documentation comments that come after  <code>context</code> 's last token and are on the same line.|

## Returns

The text of the documentation comments.

