# ImportLibrary(Library)

Method in [Library](yarn.library.md)

## Summary

Loads functions from another [Library](yarn.library.md) .

```csharp
public void ImportLibrary(Library otherLibrary)
```

## Remarks

If the other library contains a function with the same name as\
one in this library, the function in the other library takes\
precedence.

## Parameters

| Name                                         | Description                           |
| -------------------------------------------- | ------------------------------------- |
| [Yarn.Library](yarn.library.md) otherLibrary | The library to import functions from. |
