# Dialogue.Continue Method

Starts, or continues, execution of the current Program.


```csharp
public void Continue()
```
## Remarks

This method repeatedly executes instructions until one of the
following conditions is encountered:

* The [`LineHandler`](/api/csharp/yarn/dialogue.linehandler.md) or [`CommandHandler`](/api/csharp/yarn/dialogue.commandhandler.md)
is called. After calling either of these handlers, the Dialogue
will wait until [`Continue()`](/api/csharp/yarn/dialogue.continue.md) is called. Continue may
be called from inside the [`LineHandler`](/api/csharp/yarn/dialogue.linehandler.md) or [`CommandHandler`](/api/csharp/yarn/dialogue.commandhandler.md), or may be called at any future time. *
The [`OptionsHandler`](/api/csharp/yarn/dialogue.optionshandler.md) is called. When this occurs,
the Dialogue is waiting for the user to specify which of the
options has been selected, and [`SetSelectedOption(Int32)`](/api/csharp/yarn/dialogue.setselectedoption-system.int32-.md) must be called before [`Continue()`](/api/csharp/yarn/dialogue.continue.md) is called again.) * The Program reaches its
end. When this occurs, [`SetNode(String)`](/api/csharp/yarn/dialogue.setnode-system.string-.md) must be
called before [`Continue()`](/api/csharp/yarn/dialogue.continue.md) is called again. * An
error occurs while executing the Program.

This method has no effect if it is called while the [`Dialogue`](/api/csharp/yarn/dialogue.md) is currently in the process of executing
instructions.




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

* [`NodeCompleteHandler`](/api/csharp/yarn/nodecompletehandler.md): 
Represents the method that is called when the Dialogue reaches the
end of a node.

* [`DialogueCompleteHandler`](/api/csharp/yarn/dialoguecompletehandler.md): 
Represents the method that is called when the dialogue has reached
its end, and no more code remains to be run.

<div class="class-metadata">

Parent: [`Dialogue`](/api/csharp/yarn/dialogue.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L695), line 695.
