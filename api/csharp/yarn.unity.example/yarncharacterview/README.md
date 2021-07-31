# YarnCharacterView

Manager singleton that repositions DialogueUI window in 3D worldspace, based on whoever is speaking. Put this script on the same gameObject as your DialogueUI.

```csharp
public class YarnCharacterView : DialogueViewBase
```

## Fields

| Name | Description |
| :--- | :--- |
| [`allCharacters`]() |  |
| [`allCharacters`]() |  |
| [`bubbleMargin`]() |  |
| [`bubbleMargin`]() |  |
| [`canvas`]() |  |
| [`canvas`]() |  |
| [`canvasScaler`]() |  |
| [`canvasScaler`]() |  |
| [`dialogueBubbleRect`]() |  |
| [`dialogueBubbleRect`]() |  |
| [`instance`]() |  |
| [`instance`]() |  |
| [`optionsBubbleRect`]() |  |
| [`optionsBubbleRect`]() |  |
| [`playerCharacter`]() |  |
| [`playerCharacter`]() |  |

## Methods

| Name | Description |
| :--- | :--- |
| [`DismissLine(Action)`]() |  |
| [`DismissLine(Action)`]() |  |
| [`ForgetYarnCharacter(YarnCharacter)`]() | automatically called by YarnCharacter.OnDestroy\(\) to clean-up |
| [`ForgetYarnCharacter(YarnCharacter)`]() | automatically called by YarnCharacter.OnDestroy\(\) to clean-up |
| [`OnLineStatusChanged(LocalizedLine)`]() |  |
| [`OnLineStatusChanged(LocalizedLine)`]() |  |
| [`RegisterYarnCharacter(YarnCharacter)`]() | automatically called by YarnCharacter.Start\(\) so that YarnCharacterView knows they exist |
| [`RegisterYarnCharacter(YarnCharacter)`]() | automatically called by YarnCharacter.Start\(\) so that YarnCharacterView knows they exist |
| [`RunLine(LocalizedLine, Action)`]() |  |
| [`RunLine(LocalizedLine, Action)`]() |  |
| [`RunOptions(DialogueOption[], Action<Int32>)`]() |  |
| [`RunOptions(DialogueOption[], Action<Int32>)`]() |  |

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/3D/Scripts/YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/3D/Scripts/YarnCharacterView.cs#L10), line 10.

