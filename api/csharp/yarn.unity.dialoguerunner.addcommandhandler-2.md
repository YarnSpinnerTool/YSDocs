# DialogueRunner.AddCommandHandler(string,System.Func<T1, Coroutine>)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Adds a command handler. Dialogue will pause execution after the
command is called.


```csharp
public void AddCommandHandler<T1>(string commandName, System.Func<T1, Coroutine> handler)
```

## Remarks

<p>When this command handler has been added, it can be called
from your Yarn scripts like so:</p> <pre lang="yarn">
&lt;&lt;commandName param1 param2&gt;&gt;
</pre> <p>If <code>handler</code> is a method that returns a <code>Coroutine</code>, when the command is run, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will wait for the returned coroutine to stop
before delivering any more content.</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` commandName|The name of the command.|
|`System.Func<T1, Coroutine>` handler|The  <code>CommandHandler</code>  that will be invoked when the command is called.|

