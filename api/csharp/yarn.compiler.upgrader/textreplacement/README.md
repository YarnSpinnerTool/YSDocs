# TextReplacement

Contains information describing a replacement to make in a string.

```csharp
public struct TextReplacement
```

## Fields

| Name | Description |
| :--- | :--- |
| [`Comment`](textreplacement.comment.md) | A descriptive comment explaining why the substitution is necessary. |
| [`OriginalText`](textreplacement.originaltext.md) | The string to expect at [`Start`](textreplacement.start.md) in the original string. |
| [`ReplacementText`](textreplacement.replacementtext.md) | The string to replace [`OriginalText`](textreplacement.originaltext.md) with at [`Start`](textreplacement.start.md). |
| [`Start`](textreplacement.start.md) | The position in the original string where the substitution should be made. |
| [`StartLine`](textreplacement.startline.md) | The line in the original string where the substitution should be made. |

## Properties

| Name | Description |
| :--- | :--- |
| [`OriginalLength`](textreplacement.originallength.md) | Gets the length of [`OriginalText`](textreplacement.originaltext.md). |
| [`ReplacementLength`](textreplacement.replacementlength.md) | Gets the length of [`ReplacementLength`](textreplacement.replacementlength.md). |

## Namespace

[`Yarn.Compiler.Upgrader`](../)

## Assembly

YarnSpinner.Compiler.dll

## Source

Defined in [YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner.Compiler/Upgrader/LanguageUpgrader.cs#L153), line 153.

