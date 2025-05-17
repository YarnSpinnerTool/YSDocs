# Cultures.TryGetCulture(string,Culture)

Method in [Cultures](/docs/api/csharp/yarn.unity.cultures.md)

## Summary


Gets the  [Culture](yarn.unity.culture.md)  represented by the language code in
`name` .


```csharp
public static bool TryGetCulture(string name, out Culture culture)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the  [Culture](yarn.unity.culture.md)  to retrieve.|
|[Yarn.Unity.Culture](/docs/api/csharp/yarn.unity.culture.md) culture|On return, the  [Culture](yarn.unity.culture.md)  if one was found, or a default  [Culture](yarn.unity.culture.md)  if otherwise.|

## Returns

`true`  if a Culture was found;  `false`  otherwise.

