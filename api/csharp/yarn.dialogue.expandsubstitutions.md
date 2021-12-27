# Dialogue.ExpandSubstitutions(string,IList<string>)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Replaces all substitution markers in a text with the given
substitution list.


```csharp
public static string ExpandSubstitutions(string text, IList<string> substitutions)
```

## Remarks


This method replaces substitution markers - for example, `{0}`
- with the corresponding entry in  <code>substitutions</code> . If  <code>text</code>  contains a
substitution marker whose index is not present in  <code>substitutions</code> , it is ignored.


## Parameters

|Name|Description|
|:---|:---|
|text|The text containing substitution markers.|
|substitutions|The list of substitutions.|

## Returns

<code>text</code> , with the content from
<code>substitutions</code>  inserted.

