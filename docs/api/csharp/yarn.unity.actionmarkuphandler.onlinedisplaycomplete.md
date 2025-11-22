# OnLineDisplayComplete()

Method in [ActionMarkupHandler](yarn.unity.actionmarkuphandler.md)

## Summary

Called after the last call to `PresentCharacter(int, TMP_Text, CancellationToken)` .

```csharp
public abstract void OnLineDisplayComplete();
```

## Remarks

This method is an opportunity for a [ActionMarkupHandler](yarn.unity.actionmarkuphandler.md) to finalise its presentation after\
all of the characters in the line have been presented.
