# DialogueCompleteHandler Delegate

Represents the method that is called when the dialogue has reached
its end, and no more code remains to be run.


```csharp
public delegate void DialogueCompleteHandler();
```



## See Also
* [`LineHandler`](/api/csharp/yarn/linehandler.md): 
Represents the method that is called when the Dialogue delivers a
[`Line`](/api/csharp/yarn/line.md).

* [`OptionsHandler`](/api/csharp/yarn/optionshandler.md): 
Represents the method that is called when the Dialogue delivers an
[`OptionSet`](/api/csharp/yarn/optionset.md).

* [`CommandHandler`](/api/csharp/yarn/commandhandler.md): 
Represents the method that is called when the Dialogue delivers a
[`Command`](/api/csharp/yarn/command.md).

* [`NodeStartHandler`](/api/csharp/yarn/nodestarthandler.md): 
Represents the method that is called when the Dialogue begins
executing a node.

* [`NodeCompleteHandler`](/api/csharp/yarn/nodecompletehandler.md): 
Represents the method that is called when the Dialogue reaches the
end of a node.

<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L366), line 366.
