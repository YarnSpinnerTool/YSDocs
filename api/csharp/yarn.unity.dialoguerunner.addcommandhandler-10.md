# DialogueRunner.AddCommandHandler(string,System.Action<T1, T2>)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Adds a command handler. Dialogue will pause execution after the
command is called.


```csharp
public void AddCommandHandler<T1, T2>(string commandName, System.Action<T1, T2> handler)
```

## Remarks

<p>When this command handler has been added, it can be called
from your Yarn scripts like so:</p> <pre lang="yarn">
&lt;&lt;commandName param1 param2&gt;&gt;
</pre> <p>When this command handler is called, the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> will stop executing code. To make the <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> resume execution, call the onComplete action
that the <code>CommandHandler</code> receives.</p>

## Parameters

|Name|Description|
|:---|:---|
|`string` commandName|The name of the command.|
|`System.Action<T1, T2>` handler|The  <code>CommandHandler</code>  that will be invoked when the command is called.|

