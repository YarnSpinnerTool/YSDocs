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
If this value is <code>true</code>, dialogue views should
presenting the current line, so that the next piece of content can
be shown to the user.
</p> <p>
If this property is <code>true</code>, then <a href="yarn.unity.linecancellationtoken.ishurryuprequested.md">IsHurryUpRequested</a> will also be true.</p>

