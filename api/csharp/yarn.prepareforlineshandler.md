# PrepareForLinesHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the dialogue anticipates that
it will deliver lines.


```csharp
public delegate void PrepareForLinesHandler(IEnumerable<string> lineIDs);
```

## Remarks

<p>
This method should begin preparing to run the lines. For example, if a
game delivers dialogue via voice-over, the appropriate audio files
should be loaded.
</p> <p>
This method serves to provide a hint to the game that a line _may_ be
run. Not every line indicated in <code>lineIDs</code> may end up
actually running.
</p> <p>
This method may be called any number of times during a dialogue session.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<string>` lineIDs|The collection of line IDs that may be delivered at some point soon.|

