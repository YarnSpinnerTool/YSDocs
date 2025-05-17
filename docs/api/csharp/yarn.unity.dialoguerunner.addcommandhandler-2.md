# DialogueRunner.AddCommandHandler(string,MethodInfo)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Adds a command handler. Dialogue will pause execution after the
command is called.


```csharp
public void AddCommandHandler(string commandName, MethodInfo method);
```

## Remarks

<p>When this command handler has been added, it can be called
from your Yarn scripts like so:</p> <pre lang="yarn">
&lt;&lt;commandName param1 param2&gt;&gt;
</pre> <p>If `handler` is a method that returns a `UnityEngine.Coroutine`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will wait for the returned coroutine to stop
before delivering any more content.</p> <p>If `handler` is a method that returns an `System.Collections.IEnumerator`, when the command is run, the [DialogueRunner](yarn.unity.dialoguerunner.md) will start a coroutine using that method and
wait for that coroutine to stop before delivering any more content.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` commandName|The name of the command.|
| handler|The  [CommandHandler](yarn.commandhandler.md)  that will be invoked when the command is called.|
| commandName|The name of the command.|
| methodInfo|The method that will be invoked when the command is called.|
|`MethodInfo` method||

