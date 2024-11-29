# Dialogue.ContentSaliencyStrategy

Property in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets or sets the content saliency strategy used by this  <a href="yarn.dialogue.md">Dialogue</a> .


```csharp
public Saliency.IContentSaliencyStrategy ContentSaliencyStrategy
{
            get; set; }
```

## Remarks


A content saliency strategy is a class that implements  <a href="yarn.saliency.icontentsaliencystrategy.md">IContentSaliencyStrategy</a>  and selects the most
appropriate content in a line group, or any other situation where
content saliency is relevant.


