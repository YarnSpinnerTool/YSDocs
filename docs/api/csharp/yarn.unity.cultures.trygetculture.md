# Cultures.TryGetCulture(string,Culture)

Method in [Cultures](/docs/api/csharp/yarn.unity.cultures.md)

## Summary


Gets the  <a href="yarn.unity.culture.md">Culture</a>  represented by the language code in
`name` .


```csharp
public static bool TryGetCulture(string name, out Culture culture)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the  <a href="yarn.unity.culture.md">Culture</a>  to retrieve.|
|[Yarn.Unity.Culture](/docs/api/csharp/yarn.unity.culture.md) culture|On return, the  <a href="yarn.unity.culture.md">Culture</a>  if one was found, or a default  <a href="yarn.unity.culture.md">Culture</a>  if otherwise.|

## Returns

`true`  if a Culture was found;  `false`  otherwise.

