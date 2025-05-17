# LineCancellationToken.IsNextLineRequested

Property in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

## Summary


Gets a value indicating whether the dialogue runner has requested
that the next line be shown.


```csharp
public readonly bool IsNextLineRequested { get };
```

## Remarks

<p>
If this value is `true`, dialogue views should
presenting the current line, so that the next piece of content can
be shown to the user.
</p> <p>
If this property is `true`, then [IsHurryUpRequested](yarn.unity.linecancellationtoken.ishurryuprequested.md) will also be true.</p>

