# IActionRegistration.RemoveFunction(string)

Method in [IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md)

## Summary


Remove a registered function.


```csharp
void RemoveFunction(string name);
```

## Remarks


After a function has been removed, it cannot be called from
Yarn scripts.


## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the function to remove.|

## See Also

* AddFunction\<TResult\>\(string, Func\<TResult\>\)

