# LocalizedLine

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


Represents a line, ready to be presented to the user in the localisation
they have specified.


```csharp
public class LocalizedLine
```

## Fields

|Name|Description|
|:---|:---|
|[Asset](/docs/api/csharp/yarn.unity.localizedline.asset.md)|The asset associated with this line, if any.|
|[InvalidLine](/docs/api/csharp/yarn.unity.localizedline.invalidline.md)|A  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  object that represents content not being found.|
|[Metadata](/docs/api/csharp/yarn.unity.localizedline.metadata.md)|Any metadata associated with this line.|
|[RawText](/docs/api/csharp/yarn.unity.localizedline.rawtext.md)|DialogueLine's text|
|[Source](/docs/api/csharp/yarn.unity.localizedline.source.md)|The object that created this line. Most of the time will be the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  that passed the presenter the line.|
|[Substitutions](/docs/api/csharp/yarn.unity.localizedline.substitutions.md)|DialogueLine's inline expression's substitution|
|[TextID](/docs/api/csharp/yarn.unity.localizedline.textid.md)|DialogueLine's ID|

## Properties

|Name|Description|
|:---|:---|
|[CharacterName](/docs/api/csharp/yarn.unity.localizedline.charactername.md)|The name of the character, if present.|
|[Text](/docs/api/csharp/yarn.unity.localizedline.text.md)|The underlying  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  for this line.|
|[TextWithoutCharacterName](/docs/api/csharp/yarn.unity.localizedline.textwithoutcharactername.md)|The underlying  <a href="yarn.markup.markupparseresult.md">MarkupParseResult</a>  for this line, with any `character` attribute removed.|

