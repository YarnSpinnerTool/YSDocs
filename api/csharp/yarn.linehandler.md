# LineHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue delivers a
<a href="yarn.line.md">Line</a> .


```csharp
public delegate void LineHandler(Line line);
```

## Parameters

|Name|Description|
|:---|:---|
|line|The  <a href="yarn.line.md">Line</a>  that has been delivered.|

## See Also

* [OptionsHandler](/api/csharp/yarn.optionshandler.md)
* [CommandHandler](/api/csharp/yarn.commandhandler.md)
* [NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)

