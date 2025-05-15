# DialogueCompleteHandler

Delegate in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.MulticastDelegate`

## Summary


Represents the method that is called when the dialogue has reached its
end, and no more code remains to be run.


```csharp
public delegate void DialogueCompleteHandler();
```

## See Also

* [LineHandler](/docs/api/csharp/yarn.linehandler.md): Represents the method that is called when the Dialogue delivers a  [Line](yarn.line.md) .
* [OptionsHandler](/docs/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an  [OptionSet](yarn.optionset.md) .
* [CommandHandler](/docs/api/csharp/yarn.commandhandler.md): Represents the method that is called when the Dialogue delivers a  [Command](yarn.command.md) .
* [NodeStartHandler](/docs/api/csharp/yarn.nodestarthandler.md): Represents the method that is called when the Dialogue begins executing a node.
* [NodeCompleteHandler](/docs/api/csharp/yarn.nodecompletehandler.md): Represents the method that is called when the Dialogue reaches the end of a node.

