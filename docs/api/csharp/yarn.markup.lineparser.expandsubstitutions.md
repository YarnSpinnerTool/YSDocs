# ExpandSubstitutions(string,IList\<string>)

Method in [LineParser](yarn.markup.lineparser.md)

## Summary

Replaces all substitution markers in a text with the given\
substitution list.

```csharp
public static string ExpandSubstitutions(string text, IList<string> substitutions)
```

## Remarks

This method replaces substitution markers - for example, `{0}`

* with the corresponding entry in `substitutions` .\
  If `text` contains a substitution marker whose\
  index is not present in `substitutions` , it is\
  ignored.

## Parameters

| Name                                                     | Description                               |
| -------------------------------------------------------- | ----------------------------------------- |
| `string` text                                            | The text containing substitution markers. |
| `System.Collections.Generic.IList<string>` substitutions | The list of substitutions.                |

## Returns

`text` , with the content from `substitutions` inserted.
