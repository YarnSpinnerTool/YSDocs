# TemporalMarkupHandler.OnLineDisplayComplete()

Method in [TemporalMarkupHandler](/docs/api/csharp/yarn.unity.temporalmarkuphandler.md)

## Summary


Called after the last call to  <a href="yarn.unity.temporalmarkuphandler.presentcharacter.md">PresentCharacter(int,TMP_Text,CancellationToken)</a> .


```csharp
public abstract void OnLineDisplayComplete();
```

## Remarks

This method is an opportunity for a  <a href="yarn.unity.temporalmarkuphandler.md">TemporalMarkupHandler</a>  to finalise its presentation after
all of the characters in the line have been presented.

