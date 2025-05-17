# LineCancellationToken.IsHurryUpRequested

Property in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

## Summary


Gets a value indicating whether the user has requested that the line
be hurried up.


```csharp
public readonly bool IsHurryUpRequested { get }
```

## Remarks

<p>If this value is <code>true</code>, dialogue
views should speed up any ongoing delivery of the line, such as
on-screen animations, but are not required to finish delivering the
line entirely (that is, UI elements may remain on screen).</p> <p>If <a href="yarn.unity.linecancellationtoken.isnextlinerequested.md">IsNextLineRequested</a> is <code>true</code>, then this property will also be <code>true</code>.</p>

