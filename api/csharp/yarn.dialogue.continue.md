# Continue()

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Starts, or continues, execution of the current Program.


```csharp
public void Continue()
```

## Remarks


This method repeatedly executes instructions until one of the
following conditions is encountered:

* The  <a href="yarn.dialogue.linehandler.md">LineHandler</a>  or  <a href="yarn.dialogue.commandhandler.md">CommandHandler</a> 
is called. After calling either of these handlers, the Dialogue
will wait until  <a href="yarn.dialogue.continue.md">Continue()</a>  is called. Continue may
be called from inside the  <a href="yarn.dialogue.linehandler.md">LineHandler</a>  or  <a href="yarn.dialogue.commandhandler.md">CommandHandler</a> , or may be called at any future time. *
The  <a href="yarn.dialogue.optionshandler.md">OptionsHandler</a>  is called. When this occurs,
the Dialogue is waiting for the user to specify which of the
options has been selected, and  <a href="yarn.dialogue.setselectedoption.md">SetSelectedOption(int)</a>  must be called before  <a href="yarn.dialogue.continue.md">Continue()</a>  is called again.) * The Program reaches its
end. When this occurs,  <a href="yarn.dialogue.setnode.md">SetNode(string)</a>  must be
called before  <a href="yarn.dialogue.continue.md">Continue()</a>  is called again. * An
error occurs while executing the Program.

This method has no effect if it is called while the  <a href="yarn.dialogue.md">Dialogue</a>  is currently in the process of executing
instructions.


## Returns



## See Also

* [LineHandler](/api/csharp/yarn.linehandler.md)
* [OptionsHandler](/api/csharp/yarn.optionshandler.md)
* [CommandHandler](/api/csharp/yarn.commandhandler.md)
* [NodeCompleteHandler](/api/csharp/yarn.nodecompletehandler.md)
* [DialogueCompleteHandler](/api/csharp/yarn.dialoguecompletehandler.md)
