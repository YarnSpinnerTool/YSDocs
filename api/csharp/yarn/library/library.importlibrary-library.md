# ImportLibrary\(Library\)

Loads functions from another [`Library`](./).

```csharp
public void ImportLibrary(Library otherLibrary)
```

## Remarks

If the other library contains a function with the same name as one in this library, the function in the other library takes precedence.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Library`](./) otherLibrary | The library to import functions from. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Library.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Library.cs#L51), line 51.

