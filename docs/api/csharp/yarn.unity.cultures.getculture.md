# GetCulture(string)

Method in [Cultures](yarn.unity.cultures.md)

{% hint style="warning" %}
This method is obsolete and may be removed from a future version of Yarn Spinner: Use TryGetCulture, which does not throw if the culture can't be found.
{% endhint %}

## Summary

Returns the [Culture](yarn.unity.culture.md) represented by the language code\
in `name` .

```csharp
public static Culture GetCulture(string name)
```

## Parameters

| Name          | Description                                                   |
| ------------- | ------------------------------------------------------------- |
| `string` name | The name of the [Culture](yarn.unity.culture.md) to retrieve. |

## Returns

The [Culture](yarn.unity.culture.md) .
