# YarnCharacterView

Manager singleton that repositions DialogueUI window in 3D worldspace, based on whoever is speaking. Put this script on the same gameObject as your DialogueUI.

```csharp
public class YarnCharacterView : DialogueViewBase
```

## Fields

| Name                                     | Description |
| ---------------------------------------- | ----------- |
| [`allCharacters`](broken-reference)      |             |
| [`allCharacters`](broken-reference)      |             |
| [`bubbleMargin`](broken-reference)       |             |
| [`bubbleMargin`](broken-reference)       |             |
| [`canvas`](broken-reference)             |             |
| [`canvas`](broken-reference)             |             |
| [`canvasScaler`](broken-reference)       |             |
| [`canvasScaler`](broken-reference)       |             |
| [`dialogueBubbleRect`](broken-reference) |             |
| [`dialogueBubbleRect`](broken-reference) |             |
| [`instance`](broken-reference)           |             |
| [`instance`](broken-reference)           |             |
| [`optionsBubbleRect`](broken-reference)  |             |
| [`optionsBubbleRect`](broken-reference)  |             |
| [`playerCharacter`](broken-reference)    |             |
| [`playerCharacter`](broken-reference)    |             |

## Methods

| Name                                                              | Description                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| [`DismissLine(Action)`](broken-reference)                         |                                                                                          |
| [`DismissLine(Action)`](broken-reference)                         |                                                                                          |
| [`ForgetYarnCharacter(YarnCharacter)`](broken-reference)          | automatically called by YarnCharacter.OnDestroy() to clean-up                            |
| [`ForgetYarnCharacter(YarnCharacter)`](broken-reference)          | automatically called by YarnCharacter.OnDestroy() to clean-up                            |
| [`OnLineStatusChanged(LocalizedLine)`](broken-reference)          |                                                                                          |
| [`OnLineStatusChanged(LocalizedLine)`](broken-reference)          |                                                                                          |
| [`RegisterYarnCharacter(YarnCharacter)`](broken-reference)        | automatically called by YarnCharacter.Start() so that YarnCharacterView knows they exist |
| [`RegisterYarnCharacter(YarnCharacter)`](broken-reference)        | automatically called by YarnCharacter.Start() so that YarnCharacterView knows they exist |
| [`RunLine(LocalizedLine, Action)`](broken-reference)              |                                                                                          |
| [`RunLine(LocalizedLine, Action)`](broken-reference)              |                                                                                          |
| [`RunOptions(DialogueOption[], Action<Int32>)`](broken-reference) |                                                                                          |
| [`RunOptions(DialogueOption[], Action<Int32>)`](broken-reference) |                                                                                          |

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples\~/3D/Scripts/YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/develop/Samples\~/3D/Scripts/YarnCharacterView.cs#L10), line 10.
