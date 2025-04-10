# LocalizedLine

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `System.Object`

## Summary

Represents a line, ready to be presented to the user in the localisation they have specified.

```csharp
public class LocalizedLine
```

## Fields

| Name                                                       | Description                                                                                    |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [Asset](yarn.unity.localizedline.asset.md)                 | The asset associated with this line, if any.                                                   |
| [InvalidLine](yarn.unity.localizedline.invalidline.md)     | A [LocalizedLine](yarn.unity.localizedline.md) object that represents content not being found. |
| [Metadata](yarn.unity.localizedline.metadata.md)           | Any metadata associated with this line.                                                        |
| [RawText](yarn.unity.localizedline.rawtext.md)             | DialogueLine's text                                                                            |
| [Substitutions](yarn.unity.localizedline.substitutions.md) | DialogueLine's inline expression's substitution                                                |
| [TextID](yarn.unity.localizedline.textid.md)               | DialogueLine's ID                                                                              |

## Properties

| Name                                                                             | Description                                                                                                                 |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| [CharacterName](yarn.unity.localizedline.charactername.md)                       | The name of the character, if present.                                                                                      |
| [Text](yarn.unity.localizedline.text.md)                                         | The underlying [MarkupParseResult](yarn.markup.markupparseresult.md) for this line.                                         |
| [TextWithoutCharacterName](yarn.unity.localizedline.textwithoutcharactername.md) | The underlying [MarkupParseResult](yarn.markup.markupparseresult.md) for this line, with any `character` attribute removed. |
