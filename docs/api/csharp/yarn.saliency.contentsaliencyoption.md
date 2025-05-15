# ContentSaliencyOption

Class in [Yarn.Saliency](/docs/api/csharp/yarn.saliency.md)

Inherits from `System.Object`

## Summary


Represents a piece of content that may be selected by an  [IContentSaliencyStrategy](yarn.saliency.icontentsaliencystrategy.md) .


```csharp
public sealed class ContentSaliencyOption
```

## Constructors

|Name|Description|
|:---|:---|
|[ContentSaliencyOption(string)](/docs/api/csharp/yarn.saliency.contentsaliencyoption..ctor.md)|Initializes a new instance of the ContentSaliencyOption class with the specified content ID.|

## Properties

|Name|Description|
|:---|:---|
|[ComplexityScore](/docs/api/csharp/yarn.saliency.contentsaliencyoption.complexityscore.md)|Gets the complexity score of this option.|
|[ContentID](/docs/api/csharp/yarn.saliency.contentsaliencyoption.contentid.md)|Gets a string that uniquely identifies this content.|
|[ContentType](/docs/api/csharp/yarn.saliency.contentsaliencyoption.contenttype.md)|Gets the type of content that this option represents.|
|[FailingConditionValueCount](/docs/api/csharp/yarn.saliency.contentsaliencyoption.failingconditionvaluecount.md)|Get the number of conditions that failed for this piece of content.|
|[PassingConditionValueCount](/docs/api/csharp/yarn.saliency.contentsaliencyoption.passingconditionvaluecount.md)|Gets the number of conditions that passed for this piece of content.|
|[ViewCountKey](/docs/api/csharp/yarn.saliency.contentsaliencyoption.viewcountkey.md)|Gets a unique variable name that can be used for tracking the view count of a specific piece of content. This value is  `null`  if  [ContentID](yarn.saliency.contentsaliencyoption.contentid.md)  is  `null`  or empty.|

