# OptionsHandler

Delegate in [Yarn](/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the Dialogue delivers an
<a href="yarn.optionset.md">OptionSet</a> .


```csharp
public delegate void OptionsHandler(OptionSet options);
```

## Parameters

|Name|Description|
|:---|:---|
|options|The  <a href="yarn.optionset.md">OptionSet</a>  that has been delivered.|

## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md)
* [CommandHandler](/api/csharp/yarn.commandhandler.md)
* [NodeStartHandler](/api/csharp/yarn.nodestarthandler.md)
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)

