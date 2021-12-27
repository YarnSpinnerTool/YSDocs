# LineProviderBehaviour.LinesAvailable

Property in [LineProviderBehaviour](/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Gets a value indicating whether this line provider is ready to
provide  <a href="yarn.unity.localizedline.md">LocalizedLine</a>  objects. The default
implementation returns  <code>true</code> .


```csharp
public virtual bool LinesAvailable { get };
```

## Remarks


Subclasses should return  <code>false</code>  when the
required resources needed to deliver lines are not yet ready,
and  <code>true</code>  when they are.


