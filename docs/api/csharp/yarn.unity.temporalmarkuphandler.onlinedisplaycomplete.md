# OnLineDisplayComplete()

Method in [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md)

## Summary

Called after the last call to [PresentCharacter(int,TMP\_Text,CancellationToken)](yarn.unity.temporalmarkuphandler.presentcharacter.md) .

```csharp
public abstract void OnLineDisplayComplete();
```

## Remarks

This method is an opportunity for a [TemporalMarkupHandler](yarn.unity.temporalmarkuphandler.md) to finalise its presentation after all of the characters in the line have been presented.
