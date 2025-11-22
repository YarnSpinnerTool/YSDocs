# ContentType

Property in [ContentSaliencyOption](yarn.saliency.contentsaliencyoption.md)

## Summary

Gets the type of content that this option represents.

```csharp
public ContentSaliencyContentType ContentType { get; set; }
```

## Remarks

This information may be used by custom [IContentSaliencyStrategy](yarn.saliency.icontentsaliencystrategy.md) classes to allow them to have\
different behaviour depending on the type of the content.
