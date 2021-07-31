# LineProviderBehaviour

A  that produces [`LocalizedLine`](../localizedline/)s.

```csharp
public abstract class LineProviderBehaviour : MonoBehaviour
```

## Remarks

[`DialogueRunner`](../dialoguerunner/)s use a [`LineProviderBehaviour`](./) to get [`LocalizedLine`](../localizedline/)s, which contain the localized information that [`DialogueViewBase`](../dialogueviewbase/) classes use to present content to the player.

Subclasses of this abstract class may return subclasses of LocalizedLine. For example, [`AudioLineProvider`](../audiolineprovider/) returns an [`AudioLocalizedLine`](../audiolocalizedline/), which includes ; views that make use of audio can then access this additional data.

## Properties

| Name | Description |
| :--- | :--- |
| [`CurrentTextLanguageCode`](lineproviderbehaviour.currenttextlanguagecode.md) |  |
| [`LinesAvailable`](lineproviderbehaviour.linesavailable.md) |  |

## Methods

| Name | Description |
| :--- | :--- |
| [`GetLocalizedLine(Line)`](lineproviderbehaviour.getlocalizedline-yarn.line.md) |  |
| [`PrepareForLines(IEnumerable<String>)`](lineproviderbehaviour.prepareforlines-ienumerable-system.string.md) |  |
| [`Start()`](lineproviderbehaviour.start.md) |  |

## Fields

| Name | Description |
| :--- | :--- |
| [`localizationDatabase`](lineproviderbehaviour.localizationdatabase.md) | The data source for this line provider. |
| [`textLanguageCodeOverride`](lineproviderbehaviour.textlanguagecodeoverride.md) | Specifies the language code to use for text content for this [`LineProviderBehaviour`](./), overriding project settings. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/LineProviders/LineProviderBase.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/LineProviders/LineProviderBase.cs#L23), line 23.

