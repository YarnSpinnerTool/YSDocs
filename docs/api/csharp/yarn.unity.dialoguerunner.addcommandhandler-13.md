# DialogueRunner.AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, Coroutine>)

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Adds a command handler. Dialogue will pause execution after the
command is called.


```csharp
public void AddCommandHandler<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10>(string commandName, System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, Coroutine> handler);
```

## Remarks

<p>When this command handler has been added, it can be called
from your Yarn scripts like so:</p> <pre lang="yarn">
&lt;&lt;commandName param1 param2&gt;&gt;
</pre> <p>If <code>handler</code> is a method that returns a <code>UnityEngine.Coroutine</code>, when the command is run, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will wait for the returned coroutine to stop
before delivering any more content.</p> <p>If <code>handler</code> is a method that returns an <code>System.Collections.IEnumerator</code>, when the command is run, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will start a coroutine using that method and
wait for that coroutine to stop before delivering any more content.
</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` commandName|The name of the command.|
|`Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, Coroutine>` handler|The  <a href="yarn.commandhandler.md">CommandHandler</a>  that will be invoked when the command is called.|

