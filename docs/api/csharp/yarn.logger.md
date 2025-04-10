# Logger

Delegate in [Yarn](yarn.md)

Inherits from `System.MulticastDelegate`

## Summary

Represents a method that receives diagnostic messages and error information from a [Dialogue](yarn.dialogue.md) .

```csharp
public delegate void Logger(string message);
```

## Remarks

The text that this delegate receives may be output to a console, or sent to a log.

## Parameters

| Name             | Description                     |
| ---------------- | ------------------------------- |
| `string` message | The text that should be logged. |
