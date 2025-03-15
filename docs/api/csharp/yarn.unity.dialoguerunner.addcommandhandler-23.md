# AddCommandHandler(string,System.Func\<T1, T2, T3, T4, T5, T6, T7, T8, T9, IEnumerator>)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Adds a command handler. Dialogue will pause execution after the command is called.

```csharp
public void AddCommandHandler<T1, T2, T3, T4, T5, T6, T7, T8, T9>(string commandName, System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, IEnumerator> handler);
```

## Remarks

When this command handler has been added, it can be called from your Yarn scripts like so:

```
<<commandName param1 param2>>
```

If `handler` is a method that returns a `UnityEngine.Coroutine`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will wait for the returned coroutine to stop before delivering any more content.

If `handler` is a method that returns an `System.Collections.IEnumerator`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will start a coroutine using that method and wait for that coroutine to stop before delivering any more content.

## Parameters

| Name                                                            | Description                                                                                   |
| --------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `string` commandName                                            | The name of the command.                                                                      |
| `Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, IEnumerator>` handler | The [CommandHandler](yarn.commandhandler.md) that will be invoked when the command is called. |
