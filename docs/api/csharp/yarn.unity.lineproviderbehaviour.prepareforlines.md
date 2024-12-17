# LineProviderBehaviour.PrepareForLines(IEnumerable<string>)

Method in [LineProviderBehaviour](/docs/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Signals to the line provider that lines with the provided line
IDs may be presented shortly.        


```csharp
public virtual void PrepareForLines(IEnumerable<string> lineIDs)
```

## Remarks

<p>
Subclasses of <a href="yarn.unity.lineproviderbehaviour.md">LineProviderBehaviour</a> can override
this to prepare any neccessary resources needed to present
these lines, like pre-loading voice-over audio. The default
implementation does nothing.
</p> <p>
{% hint style="info" %}

Not every line may run; this method serves as a way to give the
line provider advance notice that a line <i>may</i> run, not <i>will</i>
run.

{% endhint %}
</p> <p>
When this method is run, the value returned by the <a href="yarn.unity.lineproviderbehaviour.linesavailable.md">LinesAvailable</a> property should change to false until the
necessary resources have loaded.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<string>` lineIDs|A collection of line IDs that the line provider should prepare for.|

