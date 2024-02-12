# PrepareForLinesHandler

Delegate in [Yarn](./)

Inherits from `System.MulticastDelegate`

## Summary

Represents the method that is called when the dialogue anticipates that it will deliver lines.

```csharp
public delegate void PrepareForLinesHandler(IEnumerable<string> lineIDs);
```

## Remarks

This method should begin preparing to run the lines. For example, if a game delivers dialogue via voice-over, the appropriate audio files should be loaded.

This method serves to provide a hint to the game that a line \_may\_ be run. Not every line indicated in `lineIDs` may end up actually running.

This method may be called any number of times during a dialogue session.

## Parameters

| Name                                                     | Description                                                          |
| -------------------------------------------------------- | -------------------------------------------------------------------- |
| `System.Collections.Generic.IEnumerable<string>` lineIDs | The collection of line IDs that may be delivered at some point soon. |
