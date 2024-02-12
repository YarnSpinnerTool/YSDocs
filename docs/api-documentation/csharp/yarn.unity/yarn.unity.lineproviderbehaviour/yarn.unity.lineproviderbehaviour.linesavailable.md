# LinesAvailable

Property in [LineProviderBehaviour](./)

## Summary

Gets a value indicating whether this line provider is ready to provide [LocalizedLine](../yarn.unity.localizedline/) objects. The default implementation returns `true` .

```csharp
public virtual bool LinesAvailable { get };
```

## Remarks

Subclasses should return `false` when the required resources needed to deliver lines are not yet ready, and `true` when they are.
