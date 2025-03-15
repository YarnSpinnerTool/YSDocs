# AddCommandHandler(string,System.Func\<T1, T2, Coroutine>)

Method in [IActionRegistration](yarn.unity.iactionregistration.md)

## Summary

Adds a command handler. Dialogue will pause execution after the command is called.

```csharp
void AddCommandHandler<T1, T2>(string commandName, System.Func<T1, T2, Coroutine> handler);
```

## Remarks

When this command handler has been added, it can be called from your Yarn scripts like so:

```
<<commandName param1 param2>>
```

If `handler` is a method that returns a `UnityEngine.Coroutine`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will wait for the returned coroutine to stop before delivering any more content.

If `handler` is a method that returns an `System.Collections.IEnumerator`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will start a coroutine using that method and wait for that coroutine to stop before delivering any more content.

## Parameters

| Name                              | Description                                                                                   |
| --------------------------------- | --------------------------------------------------------------------------------------------- |
| `string` commandName              | The name of the command.                                                                      |
| `Func<T1, T2, Coroutine>` handler | The [CommandHandler](yarn.commandhandler.md) that will be invoked when the command is called. |
