# ActionMarkupHandler

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

This is an abstract monobehaviour that conforms to the [IActionMarkupHandler](yarn.unity.iactionmarkuphandler.md) interface.

```csharp
public abstract class ActionMarkupHandler : MonoBehaviour, IActionMarkupHandler
```

## Remarks

Intended to be used in situations where you require a monobehaviour version of the interfaces.\
This is used by [LinePresenter](yarn.unity.linepresenter.md) to have a list of handlers that can be connected up via the inspector.

## Methods

| Name                                                                                                                      | Description                                                                          |
| ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| [OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)](yarn.unity.actionmarkuphandler.oncharacterwillappear.md) | Called repeatedly for each visible character in the line.                            |
| [OnLineDisplayBegin(MarkupParseResult,TMP\_Text)](yarn.unity.actionmarkuphandler.onlinedisplaybegin.md)                   | Called immediately before the first character in the line is presented.              |
| [OnLineDisplayComplete()](yarn.unity.actionmarkuphandler.onlinedisplaycomplete.md)                                        | Called after the last call to `PresentCharacter(int, TMP_Text, CancellationToken)` . |
| [OnLineWillDismiss()](yarn.unity.actionmarkuphandler.onlinewilldismiss.md)                                                | Called right before the line will dismiss itself.                                    |
| [OnPrepareForLine(MarkupParseResult,TMP\_Text)](yarn.unity.actionmarkuphandler.onprepareforline.md)                       | Called when the line view receives the line, to prepare for showing the line.        |
