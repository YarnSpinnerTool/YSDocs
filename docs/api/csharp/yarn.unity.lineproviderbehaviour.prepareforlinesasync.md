# PrepareForLinesAsync(IEnumerable\<string>,CancellationToken)

Method in [LineProviderBehaviour](yarn.unity.lineproviderbehaviour.md)

## Summary

Signals to the line provider that lines with the provided line IDs may be presented shortly.

```csharp
public virtual YarnTask PrepareForLinesAsync(IEnumerable<string> lineIDs, CancellationToken cancellationToken)
```

## Remarks

This method allows implementing classes a chance to prepare any neccessary resources needed to present these lines, like pre-loading voice-over audio. The default implementation does nothing.

{% hint style="info" %}
Not every line may run; this method serves as a way to give the line provider advance notice that a line _may_ run, not _will_ run.
{% endhint %}

## Parameters

| Name                                  | Description                                                                    |
| ------------------------------------- | ------------------------------------------------------------------------------ |
| `IEnumerable<string>` lineIDs         | A collection of line IDs that the line provider should prepare for.            |
| `CancellationToken` cancellationToken | A cancellation token that indicates whether the operation should be cancelled. |
