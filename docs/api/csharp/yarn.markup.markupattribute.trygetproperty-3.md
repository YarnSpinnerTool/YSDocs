# MarkupAttribute.TryGetProperty(string,int)

Method in [MarkupAttribute](/docs/api/csharp/yarn.markup.markupattribute.md)

## Summary


Gets an integer property named  `name`  from this
attribute, if present.


```csharp
public readonly bool TryGetProperty(string name, out int result)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the property.|
|`int` result|On return, the property's value if found, or zero if not.|

## Returns

`true`  if a property named  `name`  was found;  `false` 
otherwise.

