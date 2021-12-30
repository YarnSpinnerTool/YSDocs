# LineStatus

Enum in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `System.Enum`

## Summary


The presentation status of a  <a href="yarn.unity.localizedline.md">LocalizedLine</a> .


```csharp
public enum LineStatus
{
    Presenting,
    Interrupted,
    FinishedPresenting,
    Dismissed
}
```

## Members

|Name|Description|
|:---|:---|
|[Dismissed](/api/csharp/yarn.unity.linestatus.dismissed.md)|The line is not being presented anymore in any way to the user.|
|[FinishedPresenting](/api/csharp/yarn.unity.linestatus.finishedpresenting.md)|The line has finished being delivered to the user.|
|[Interrupted](/api/csharp/yarn.unity.linestatus.interrupted.md)|The user has interrupted the delivery of this line, by calling <a href="yarn.unity.dialogueviewbase.readyfornextline.md">ReadyForNextLine()</a>  before all line views finished delivering the line. All line views should finish delivering the line as quickly as possible, and then signal that the line has been  <a href="yarn.unity.linestatus.finishedpresenting.md">FinishedPresenting</a> .|
|[Presenting](/api/csharp/yarn.unity.linestatus.presenting.md)|The line is in the process of being presented to the user, but has not yet finished appearing.|

