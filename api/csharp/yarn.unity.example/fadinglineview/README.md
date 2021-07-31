# FadingLineView

A dialogue view that presents lines in a  component, and options in a vertical list. The text fades in from transparency when delivering a line, and fades out when the line is complete. Each character can have a custom colour to use. In addition, pressing the Spacebar key will skip the line.

```csharp
public class FadingLineView : DialogueViewBase
```

## Methods

| Name | Description |
| :--- | :--- |
| [`DismissLine(Action)`]() |  |
| [`DismissLine(Action)`]() |  |
| [`GetColorForCharacter(String)`]() | Returns a Color to use for a line, based on the name of the character. |
| [`GetColorForCharacter(String)`]() | Returns a Color to use for a line, based on the name of the character. |
| [`OnLineStatusChanged(LocalizedLine)`]() |  |
| [`OnLineStatusChanged(LocalizedLine)`]() |  |
| [`OptionButtonSelected(Int32, Action<Int32>)`]() |  |
| [`OptionButtonSelected(Int32, Action<Int32>)`]() |  |
| [`RunLine(LocalizedLine, Action)`]() |  |
| [`RunLine(LocalizedLine, Action)`]() |  |
| [`RunOptions(DialogueOption[], Action<Int32>)`]() |  |
| [`RunOptions(DialogueOption[], Action<Int32>)`]() |  |

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/StartHere/Scripts/FadingLineView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/StartHere/Scripts/FadingLineView.cs#L20), line 20.

