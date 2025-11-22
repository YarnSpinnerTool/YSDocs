# MarkupAttribute.TryGetProperty(string,bool)

Method in [MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md)

## Summary


Gets a boolean property named  <code>name</code>  from this
attribute, if present.


```csharp
public readonly bool TryGetProperty(string name, out bool result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the property.|
|`bool` result|On return, the property's value if found, or <code>false</code>  if not.|

## Returns

<code>true</code>  if a property named  <code>name</code>  was found;  <code>false</code> 
otherwise.

