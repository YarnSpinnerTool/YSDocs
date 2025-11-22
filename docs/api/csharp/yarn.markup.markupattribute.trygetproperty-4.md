# MarkupAttribute.TryGetProperty(string,string?)

Method in [MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md)

## Summary


Gets a string property named  <code>name</code>  from this
attribute, if present.


```csharp
public readonly bool TryGetProperty(string name, [NotNullWhen(true)] out string? result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the property.|
|`string` result|On return, the property's value if found, or <code>null</code>  if not.|

## Returns

<code>true</code>  if a property named  <code>name</code>  was found;  <code>false</code> 
otherwise.

