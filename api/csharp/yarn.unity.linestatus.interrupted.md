# Interrupted

 in [LineStatus](/api/csharp/yarn.unity.linestatus.md)

## Summary


The user has interrupted the delivery of this line, by calling
<a href="yarn.unity.dialogueviewbase.readyfornextline.md">ReadyForNextLine()</a>  before all line
views finished delivering the line. All line views should
finish delivering the line as quickly as possible, and then
signal that the line has been  <a href="yarn.unity.linestatus.finishedpresenting.md">FinishedPresenting</a> .


```csharp
Interrupted
```

## Remarks


For example, any animations should skip to the end, either
immediately or very quickly, and any audio should stop or
quickly fade out.


