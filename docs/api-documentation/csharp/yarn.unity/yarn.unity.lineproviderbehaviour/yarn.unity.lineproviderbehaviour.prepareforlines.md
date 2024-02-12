# PrepareForLines(IEnumerable\<string>)

Method in [LineProviderBehaviour](./)

## Summary

Signals to the line provider that lines with the provided line IDs may be presented shortly.

```csharp
public virtual void PrepareForLines(IEnumerable<string> lineIDs)
```

## Remarks

Subclasses of [LineProviderBehaviour](./) can override this to prepare any neccessary resources needed to present these lines, like pre-loading voice-over audio. The default implementation does nothing.

{% hint style="info" %}
Not every line may run; this method serves as a way to give the line provider advance notice that a line _may_ run, not _will_ run.
{% endhint %}

When this method is run, the value returned by the [LinesAvailable](yarn.unity.lineproviderbehaviour.linesavailable.md) property should change to false until the necessary resources have loaded.

## Parameters

| Name                                                     | Description                                                         |
| -------------------------------------------------------- | ------------------------------------------------------------------- |
| `System.Collections.Generic.IEnumerable<string>` lineIDs | A collection of line IDs that the line provider should prepare for. |
