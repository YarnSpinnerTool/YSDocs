# MarkupAttribute.TryGetProperty(string,float)

Method in [MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md)

## Summary


Gets a float property named  <code>name</code>  from this
attribute, if present.


```csharp
public bool TryGetProperty(string name, out float result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the property.|
|`float` result|On return, the property's value if found, or zero if not.|

## Returns

<code>true</code>  if a property named  <code>name</code>  was found;  <code>false</code> 
otherwise.

