# Library.ImportLibrary(Library)

Method in [Library](/api/csharp/yarn.library.md)

## Summary


Loads functions from another  <a href="yarn.library.md">Library</a> .


```csharp
public void ImportLibrary(Library otherLibrary)
```

## Remarks


If the other library contains a function with the same name as
one in this library, the function in the other library takes
precedence.


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Library](/api/csharp/yarn.library.md) otherLibrary|The library to import functions from.|

