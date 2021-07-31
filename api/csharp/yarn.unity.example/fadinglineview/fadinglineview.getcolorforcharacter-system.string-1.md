# GetColorForCharacter\(String\)

Returns a Color to use for a line, based on the name of the character.

```csharp
public Color GetColorForCharacter(string name)
```

## Remarks

The color is looked up from the list specified in `Yarn.Unity.Example.FadingLineView.characters`. If `name` does not refer to a known character, `Yarn.Unity.Example.FadingLineView.defaultColor` is returned.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) name | The name of the character to look up a character for. |

## Return Type

`Color`: The color to use.

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/StartHere/Scripts/FadingLineView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/StartHere/Scripts/FadingLineView.cs#L70), line 70.

