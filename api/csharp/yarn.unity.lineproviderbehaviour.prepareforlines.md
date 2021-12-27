# LineProviderBehaviour.PrepareForLines(IEnumerable<string>)

Method in [LineProviderBehaviour](/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Signals to the line provider that lines with the provided line
IDs may be presented shortly.        


```csharp
public virtual void PrepareForLines(IEnumerable<string> lineIDs)
```

## Remarks


Subclasses of  <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a>  can override
this to prepare any neccessary resources needed to present
these lines, like pre-loading voice-over audio. The default
implementation does nothing.

Not every line may run; this method serves as a way to give the
line provider advance notice that a line _may_ run, not _will_
run.

When this method is run, the value returned by the  <a href="yarn.unity.lineproviderbehaviour.linesavailable.md">LinesAvailable</a>  property should change to false until the
necessary resources have loaded.


## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<string>` lineIDs|A collection of line IDs that the line provider should prepare for.|

