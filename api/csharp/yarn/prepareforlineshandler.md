# PrepareForLinesHandler Delegate

Represents the method that is called when the dialogue anticipates
that it will deliver lines.


```csharp
public delegate void PrepareForLinesHandler(IEnumerable<string> lineIDs);
```
## Remarks

This method should begin preparing to run the lines. For example,
if a game delivers dialogue via voice-over, the appropriate audio
files should be loaded.

This method serves to provide a hint to the game that a line _may_
be run. Not every line indicated in  may
end up actually running.

This method may be called any number of times during a dialogue
session.


## Parameters
|Parameter|Description|
|:---|:---|
|[`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IEnumerable{System.String}) lineIDs|The collection of line IDs that may be delivered at some point soon.|


<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L386), line 386.
