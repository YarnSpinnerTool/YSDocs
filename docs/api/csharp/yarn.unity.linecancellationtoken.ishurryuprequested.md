# IsHurryUpRequested

Property in [LineCancellationToken](yarn.unity.linecancellationtoken.md)

## Summary

Gets a value indicating whether the user has requested that the line be hurried up.

```csharp
public readonly bool IsHurryUpRequested { get };
```

## Remarks

If this value is `true`, dialogue views should speed up any ongoing delivery of the line, such as on-screen animations, but are not required to finish delivering the line entirely (that is, UI elements may remain on screen).

If [IsNextLineRequested](yarn.unity.linecancellationtoken.isnextlinerequested.md) is `true`, then this property will also be `true`.
