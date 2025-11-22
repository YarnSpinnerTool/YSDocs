# ILineProvider.PrepareForLinesAsync(IEnumerable<string>,CancellationToken)

Method in [ILineProvider](/docs/api/csharp/yarn.unity.ilineprovider.md)

## Summary


Signals to the line provider that lines with the provided line IDs may
be presented shortly.        


```csharp
public YarnTask PrepareForLinesAsync(IEnumerable<string> lineIDs, CancellationToken cancellationToken);
```

## Remarks

<p>
This method allows implementing classes a chance to prepare any
neccessary resources needed to present these lines, like pre-loading
voice-over audio. The default implementation does nothing.
</p> <p>
{% hint style="info" %}

Not every line may run; this method serves as a way to give the line
provider advance notice that a line <i>may</i> run, not <i>will</i> run.

{% endhint %}
</p>

## Parameters

|Name|Description|
|:---|:---|
|`IEnumerable<string>` lineIDs|A collection of line IDs that the line provider should prepare for.|
|`CancellationToken` cancellationToken|A cancellation token that indicates whether the operation should be cancelled.|

