# IsAvailable

Gets a value indicating whether the player should be permitted to select this option.

```csharp
public bool IsAvailable { get; }
```

## Remarks

If this value is \`\`, this option had a line condition on it that failed. The option will still be delivered to the game, but, depending on the needs of the game, the game may decide to not allow the player to select it, or not offer it to the player at all.

This is intended for situations where games wish to show options that the player _could_ have taken, if some other condition had been met \(e.g. having enough "charisma" points\).

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L152), line 152.

