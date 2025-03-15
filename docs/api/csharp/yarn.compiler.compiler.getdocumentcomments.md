# GetDocumentComments(CommonTokenStream,ParserRuleContext,bool)

Method in [Compiler](yarn.compiler.compiler.md)

## Summary

Gets the text of the documentation comments that either immediately precede `context` , or are on the same line as `context` .

```csharp
public static string GetDocumentComments(CommonTokenStream tokens, ParserRuleContext context, bool allowCommentsAfter = true)
```

## Remarks

Documentation comments begin with a triple-slash ( `///` ), and are used to describe variable declarations. If documentation comments precede a declaration (that is, they're not on the same line as the declaration), then they may span multiple lines, as long as each line begins with a triple-slash.

## Parameters

| Name                                       | Description                                                                                                                   |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| `Antlr4.Runtime.CommonTokenStream` tokens  | The token stream to search.                                                                                                   |
| `Antlr4.Runtime.ParserRuleContext` context | The parser rule context to get documentation comments for.                                                                    |
| `bool` allowCommentsAfter                  | If true, this method will search for documentation comments that come after `context` 's last token and are on the same line. |

## Returns

The text of the documentation comments.
