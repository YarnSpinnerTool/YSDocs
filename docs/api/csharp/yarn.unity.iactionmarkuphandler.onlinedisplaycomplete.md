# IActionMarkupHandler.OnLineDisplayComplete()

Method in [IActionMarkupHandler](/docs/api/csharp/yarn.unity.iactionmarkuphandler.md)

## Summary


Called after the last call to  `PresentCharacter(int,     TMP_Text, CancellationToken)` .


```csharp
public void OnLineDisplayComplete();
```

## Remarks

This method is an opportunity for a  <a href="yarn.unity.actionmarkuphandler.md">ActionMarkupHandler</a>  to finalise its presentation after
all of the characters in the line have been presented.

