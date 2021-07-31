# Logger

Represents a method that receives diagnostic messages and error information from a [`Dialogue`](dialogue/).

```csharp
public delegate void Logger(string message);
```

## Remarks

The text that this delegate receives may be output to a console, or sent to a log.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`string`](https://docs.microsoft.com/dotnet/api/System.String) message | The text that should be logged. |

## Namespace

[`Yarn`](./)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L193), line 193.

