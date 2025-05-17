# Dialogue.GetHeaderValue(string,string)

Method in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets the value of the header named  <code>headerName</code>  on
the node named  <code>nodeName</code> , or  <code>null</code>  if the header can't be found.


```csharp
public string? GetHeaderValue(string nodeName, string headerName)
```

## Remarks

If the node has more than one header named  <code>headerName</code> , the first one is used.

## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName|The name of the node.|
|`string` headerName|The name of the header.|

## Returns

The value of the first header on the node with the
specified header value.

