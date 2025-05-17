# Yarn.Saliency Namespace

## Summary

Contains classes for choosing the most relevant content out of a set of possible options.


## Classes

|Name|Description|
|:---|:---|
|[BestLeastRecentlyViewedSaliencyStrategy](/docs/api/csharp/yarn.saliency.bestleastrecentlyviewedsaliencystrategy.md)|A content saliency strategy that returns the first of the best, least-recently seen choices from the provided options.|
|[BestSaliencyStrategy](/docs/api/csharp/yarn.saliency.bestsaliencystrategy.md)|A content saliency strategy that returns the best of the provided options.|
|[ContentSaliencyOption](/docs/api/csharp/yarn.saliency.contentsaliencyoption.md)|Represents a piece of content that may be selected by an  <a href="yarn.saliency.icontentsaliencystrategy.md">IContentSaliencyStrategy</a> .|
|[EnumerableRandomExtension](/docs/api/csharp/yarn.saliency.enumerablerandomextension.md)|Contains extension methods for  <code>System.Collections.Generic.IEnumerable`1</code> .|
|[FirstSaliencyStrategy](/docs/api/csharp/yarn.saliency.firstsaliencystrategy.md)|A content saliency strategy that always returns the first non-failing item in the list of available options.|
|[RandomBestLeastRecentlyViewedSaliencyStrategy](/docs/api/csharp/yarn.saliency.randombestleastrecentlyviewedsaliencystrategy.md)|A content saliency strategy that returns a random choice of the best, least-recently seen choices from the provided options.|

## Enums

|Name|Description|
|:---|:---|
|[ContentSaliencyContentType](/docs/api/csharp/yarn.saliency.contentsaliencycontenttype.md)|Indicates what type of content a  <a href="yarn.saliency.contentsaliencyoption.md">ContentSaliencyOption</a>  represents.|

## Interfaces

|Name|Description|
|:---|:---|
|[IContentSaliencyStrategy](/docs/api/csharp/yarn.saliency.icontentsaliencystrategy.md)|Contains methods for choosing a piece of content from a collection of options.|

