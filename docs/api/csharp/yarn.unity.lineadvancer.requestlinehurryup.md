# RequestLineHurryUp()

Method in [LineAdvancer](yarn.unity.lineadvancer.md)

## Summary

Requests that the line be hurried up.

```csharp
public void RequestLineHurryUp()
```

## Remarks

If this method has been called more times for a single line\
than `Yarn.Unity.LineAdvancer.numberOfAdvancesThisLine` , this method requests\
that the dialogue runner proceed to the next line. Otherwise, it\
requests that the dialogue runner instruct all line views to hurry\
up their presentation of the current line.
