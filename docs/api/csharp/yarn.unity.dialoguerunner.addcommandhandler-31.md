# AddCommandHandler(string,System.Action\<T1, T2, T3, T4, T5, T6>)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Adds a command handler. Dialogue will pause execution after the command is called.

```csharp
public void AddCommandHandler<T1, T2, T3, T4, T5, T6>(string commandName, System.Action<T1, T2, T3, T4, T5, T6> handler);
```

## Remarks

When this command handler has been added, it can be called from your Yarn scripts like so:

```
<<commandName param1 param2>>
```

If `handler` is a method that returns a `UnityEngine.Coroutine`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will wait for the returned coroutine to stop before delivering any more content.

If `handler` is a method that returns an `System.Collections.IEnumerator`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will start a coroutine using that method and wait for that coroutine to stop before delivering any more content.

## Parameters

| Name                                     | Description                                                                                   |
| ---------------------------------------- | --------------------------------------------------------------------------------------------- |
| `string` commandName                     | The name of the command.                                                                      |
| `Action<T1, T2, T3, T4, T5, T6>` handler | The [CommandHandler](yarn.commandhandler.md) that will be invoked when the command is called. |
