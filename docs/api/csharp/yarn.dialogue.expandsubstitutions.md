# Dialogue.ExpandSubstitutions(string,IList<string>)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Replaces all substitution markers in a text with the given
substitution list.


```csharp
public static string ExpandSubstitutions(string text, IList<string> substitutions)
```

## Remarks


This method replaces substitution markers - for example,  <code>{0}</code> 
- with the corresponding entry in  <code>substitutions</code> .
If  <code>text</code>  contains a substitution marker whose
index is not present in  <code>substitutions</code> , it is
ignored.


## Parameters

|Name|Description|
|:---|:---|
|`string` text|The text containing substitution markers.|
|`System.Collections.Generic.IList<string>` substitutions|The list of substitutions.|

## Returns

<code>text</code> , with the content from  <code>substitutions</code>  inserted.

