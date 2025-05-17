# ActionMarkupHandler

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.MonoBehaviour`

## Summary


This is an abstract monobehaviour that conforms to the  <a href="yarn.unity.iactionmarkuphandler.md">IActionMarkupHandler</a>  interface.


```csharp
public abstract class ActionMarkupHandler : MonoBehaviour, IActionMarkupHandler
```

## Remarks

<p>
Intended to be used in situations where you require a monobehaviour version of the interfaces.
This is used by <a href="yarn.unity.linepresenter.md">LinePresenter</a> to have a list of handlers that can be connected up via the inspector.
</p>

## Methods

|Name|Description|
|:---|:---|
|[OnCharacterWillAppear(int,MarkupParseResult,CancellationToken)](/docs/api/csharp/yarn.unity.actionmarkuphandler.oncharacterwillappear.md)|Called repeatedly for each visible character in the line.|
|[OnLineDisplayBegin(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.actionmarkuphandler.onlinedisplaybegin.md)|Called immediately before the first character in the line is presented.|
|[OnLineDisplayComplete()](/docs/api/csharp/yarn.unity.actionmarkuphandler.onlinedisplaycomplete.md)|Called after the last call to  <code>PresentCharacter(int,     TMP_Text, CancellationToken)</code> .|
|[OnLineWillDismiss()](/docs/api/csharp/yarn.unity.actionmarkuphandler.onlinewilldismiss.md)|Called right before the line will dismiss itself.|
|[OnPrepareForLine(MarkupParseResult,TMP_Text)](/docs/api/csharp/yarn.unity.actionmarkuphandler.onprepareforline.md)|Called when the line view receives the line, to prepare for showing the line.|

