# IsNextLineRequested

Property in [LineCancellationToken](yarn.unity.linecancellationtoken.md)

## Summary

Gets a value indicating whether the dialogue runner has requested\
that the next line be shown.

```csharp
public readonly bool IsNextLineRequested { get }
```

## Remarks

If this value is `true`, dialogue presenters should\
presenting the current line, so that the next piece of content can\
be shown to the user.

If this property is `true`, then [IsHurryUpRequested](yarn.unity.linecancellationtoken.ishurryuprequested.md) will also be true.
