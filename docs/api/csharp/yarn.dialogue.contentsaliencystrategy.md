# Dialogue.ContentSaliencyStrategy

Property in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets or sets the content saliency strategy used by this  [Dialogue](yarn.dialogue.md) .


```csharp
public Saliency.IContentSaliencyStrategy ContentSaliencyStrategy
{
            get; set; }
```

## Remarks


A content saliency strategy is a class that implements  [IContentSaliencyStrategy](yarn.saliency.icontentsaliencystrategy.md)  and selects the most
appropriate content in a line group, or any other situation where
content saliency is relevant.


