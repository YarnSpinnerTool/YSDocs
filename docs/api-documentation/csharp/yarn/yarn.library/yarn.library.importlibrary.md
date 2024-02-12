# ImportLibrary(Library)

Method in [Library](./)

## Summary

Loads functions from another [Library](./) .

```csharp
public void ImportLibrary(Library otherLibrary)
```

## Remarks

If the other library contains a function with the same name as one in this library, the function in the other library takes precedence.

## Parameters

| Name                            | Description                           |
| ------------------------------- | ------------------------------------- |
| [Yarn.Library](./) otherLibrary | The library to import functions from. |
